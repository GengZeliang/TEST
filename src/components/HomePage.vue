<template>
  <div>
    <section class="hero">
      <h1>超值好物，尽在闪购商城</h1>
      <p>覆盖数码、服饰、美妆、家居、食品等多个品类，发现更多优质商品，享受便捷购物体验。</p>
    </section>

    <h2 class="section-title">热门分类</h2>
    <div class="category-grid">
      <div class="category-card" v-for="item in categories" :key="item.title">
        <div class="category-icon">{{ item.icon }}</div>
        <h3>{{ item.title }}</h3>
        <p>{{ item.desc }}</p>
      </div>
    </div>

    <h2 class="section-title">热门商品</h2>
    <div class="product-grid">
      <div class="product-card" v-for="product in products" :key="product.name">
        <img :src="product.img" :alt="product.name" />
        <div>
          <span class="tag" v-for="tag in product.tags" :key="tag">{{ tag }}</span>
        </div>
        <h3>{{ product.name }}</h3>
        <p>{{ product.desc }}</p>
        <div class="price">¥{{ product.price }}</div>
        <button class="btn" @click="$emit('add-to-cart', product)">加入购物车</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const categories = [
  { icon: '📱', title: '数码家电', desc: '手机、耳机、电脑' },
  { icon: '👗', title: '时尚穿搭', desc: '服饰、鞋包、配饰' },
  { icon: '🛋️', title: '家居生活', desc: '收纳、寝具、装饰' },
  { icon: '💄', title: '美妆护肤', desc: '彩妆、面膜、精华' }
]

const products = [
  {
    name: '智能降噪耳机',
    desc: '高清音质，续航持久，通勤必备。',
    price: 299,
    img: 'https://picsum.photos/400/300?random=11',
    tags: ['热卖', '包邮']
  },
  {
    name: '轻奢羽绒外套',
    desc: '保暖时尚，冬季穿搭百搭单品。',
    price: 459,
    img: 'https://picsum.photos/400/300?random=12',
    tags: ['新品', '爆款']
  },
  {
    name: '北欧风台灯',
    desc: '简约设计，柔和护眼光源。',
    price: 129,
    img: 'https://picsum.photos/400/300?random=13',
    tags: ['精选', '家居']
  },
  {
    name: '保湿精华套装',
    desc: '深层滋润，改善干燥与暗沉。',
    price: 198,
    img: 'https://picsum.photos/400/300?random=14',
    tags: ['美妆', '推荐']
  }
]
</script>
