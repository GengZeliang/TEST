<template>
  <div>
    <div class="profile-top">
      <div class="avatar">👤</div>
      <div>
        <h2>Hi，欢迎回来，用户小明</h2>
        <p style="margin-top:8px; line-height:1.7;">
          这里展示你的收藏、订单、积分、优惠券等个人信息，方便快速查看账户状态。
        </p>
      </div>
    </div>

    <div class="stats">
      <div class="stat">
        <h4>账户积分</h4>
        <div class="num">1280</div>
      </div>
      <div class="stat">
        <h4>收藏商品</h4>
        <div class="num">12</div>
      </div>
      <div class="stat">
        <h4>待支付订单</h4>
        <div class="num">3</div>
      </div>
      <div class="stat">
        <h4>优惠券</h4>
        <div class="num">5</div>
      </div>
    </div>

    <div class="profile-grid">
      <div class="info-card">
        <h3 style="margin-bottom:12px;">我的收藏</h3>
        <div class="list-item"><span>智能降噪耳机</span><span class="badge">已收藏</span></div>
        <div class="list-item"><span>北欧风台灯</span><span class="badge">已收藏</span></div>
        <div class="list-item"><span>舒适记忆枕</span><span class="badge">已收藏</span></div>
        <div class="list-item"><span>高颜值化妆箱</span><span class="badge">已收藏</span></div>
      </div>

      <div class="info-card">
        <h3 style="margin-bottom:12px;">订单信息</h3>
        <div class="list-item"><span>订单 #2025001</span><span>待发货</span></div>
        <div class="list-item"><span>订单 #2025002</span><span>待收货</span></div>
        <div class="list-item"><span>订单 #2025003</span><span>已完成</span></div>
        <div class="list-item"><span>积分兑换</span><span class="badge">可兑换优惠券</span></div>
      </div>
    </div>
  </div>
</template>
