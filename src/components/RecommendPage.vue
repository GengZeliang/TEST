<template>
  <div>
    <div class="recommend-banner">
      <h1>为你推荐</h1>
      <p>根据你的浏览习惯和兴趣推荐商品，发现更多好物。</p>
    </div>

    <div class="product-grid">
      <div class="product-card" v-for="product in recommendList" :key="product.name">
        <img :src="product.img" :alt="product.name" />
        <h3>{{ product.name }}</h3>
        <p>{{ product.desc }}</p>
        <div class="price">¥{{ product.price }}</div>
        <button class="btn" @click="$emit('add-to-cart', product)">加入购物车</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const recommendList = [
  {
    name: '运动智能手表',
    desc: '支持心率监测、运动记录与消息提醒。',
    price: 399,
    img: 'https://picsum.photos/400/300?random=21'
  },
  {
    name: '舒适记忆枕',
    desc: '贴合颈椎曲线，缓解睡眠疲劳。',
    price: 159,
    img: 'https://picsum.photos/400/300?random=22'
  },
  {
    name: '便携榨汁杯',
    desc: '随时鲜榨，适合办公与旅行。',
    price: 99,
    img: 'https://picsum.photos/400/300?random=23'
  },
  {
    name: '高颜值化妆箱',
    desc: '多层收纳，适合出行与日常整理。',
    price: 189,
    img: 'https://picsum.photos/400/300?random=24'
  }
]
</script>
