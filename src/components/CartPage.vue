<template>
  <div>
    <h2 class="section-title">购物车</h2>

    <div class="cart-summary">
      <p>当前购物车商品数量：<strong>{{ totalCount }}</strong></p>
      <p>预计总价：<strong>¥{{ totalPrice }}</strong></p>
    </div>

    <div class="cart-list" v-if="cart.length > 0">
      <div class="cart-card cart-item" v-for="(item, index) in cart" :key="index">
        <div>
          <h3>{{ item.name }}</h3>
          <p class="price">¥{{ item.price }}</p>
          <div class="qty">
            <button @click="$emit('change-qty', index, -1)">-</button>
            <span>数量：{{ item.qty }}</span>
            <button @click="$emit('change-qty', index, 1)">+</button>
          </div>
        </div>
        <div>
          <button class="btn secondary" @click="$emit('remove-item', index)">删除</button>
        </div>
      </div>
    </div>

    <div v-else class="cart-card">
      购物车为空，快去首页挑选喜欢的商品吧～
    </div>

    <div style="margin-top: 18px; display:flex; gap:10px; flex-wrap:wrap;">
      <button class="btn" @click="checkout">去结算</button>
      <button class="btn secondary" @click="$emit('clear-cart')">清空购物车</button>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  cart: {
    type: Array,
    required: true
  }
})

const totalCount = computed(() =>
  props.cart.reduce((sum, item) => sum + item.qty, 0)
)

const totalPrice = computed(() =>
  props.cart.reduce((sum, item) => sum + item.qty * item.price, 0)
)

function checkout() {
  if (props.cart.length === 0) {
    alert('购物车为空，无法结算。')
    return
  }
  alert(`模拟结算成功，总金额：¥${totalPrice.value}`)
}
</script>
