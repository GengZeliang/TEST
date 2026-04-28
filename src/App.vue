<template>
  <div>
    <header class="navbar">
      <div class="logo">闪购商城</div>
      <nav class="nav-links">
        <button :class="{ active: currentPage === 'home' }" @click="currentPage='home'">首页</button>
        <button :class="{ active: currentPage === 'recommend' }" @click="currentPage='recommend'">推荐页</button>
        <button :class="{ active: currentPage === 'cart' }" @click="currentPage='cart'">购物车</button>
        <button :class="{ active: currentPage === 'profile' }" @click="currentPage='profile'">个人页</button>
      </nav>
    </header>

    <main class="container">
      <HomePage
        v-if="currentPage === 'home'"
        @add-to-cart="addToCart"
      />
      <RecommendPage
        v-if="currentPage === 'recommend'"
        @add-to-cart="addToCart"
      />
      <CartPage
        v-if="currentPage === 'cart'"
        :cart="cart"
        @remove-item="removeItem"
        @change-qty="changeQty"
        @clear-cart="clearCart"
      />
      <ProfilePage
        v-if="currentPage === 'profile'"
      />
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import HomePage from './components/HomePage.vue'
import CartPage from './components/CartPage.vue'
import RecommendPage from './components/RecommendPage.vue'
import ProfilePage from './components/ProfilePage.vue'

const currentPage = ref('home')

const cart = ref([
  { name: '智能降噪耳机', price: 299, qty: 1 },
  { name: '北欧风台灯', price: 129, qty: 2 }
])

function addToCart(product) {
  const found = cart.value.find(item => item.name === product.name)
  if (found) {
    found.qty += 1
  } else {
    cart.value.push({ ...product, qty: 1 })
  }
  alert(`已加入购物车：${product.name}`)
  currentPage.value = 'cart'
}

function removeItem(index) {
  cart.value.splice(index, 1)
}

function changeQty(index, delta) {
  cart.value[index].qty += delta
  if (cart.value[index].qty <= 0) {
    cart.value.splice(index, 1)
  }
}

function clearCart() {
  if (confirm('确定要清空购物车吗？')) {
    cart.value = []
  }
}
</script>
