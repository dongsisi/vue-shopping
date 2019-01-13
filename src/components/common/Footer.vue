<template>
<ul class="footer-nav">
  <li>
    <router-link href="#" class="navs-item-home" to="/">
      <img src="../../assets/images/menu-icon/navs-item-home.png" alt="">
      <p>首页</p>
    </router-link>
  </li>
   <li>
    <router-link href="#" class="navs-item-menu" to="/list">
      <img src="../../assets/images/menu-icon/navs-item-menu.png" alt="">
      <p>闪送超市</p>
    </router-link>
  </li>
  <li class="cart">
    <router-link class="navs-item-cart" to="/cart">
      <img src="../../assets/images/menu-icon/navs-item-cart.png" alt="" class="active">
      <p>购物车</p>
      <div class="navs-bubble">0</div>
    </router-link>
  </li>
  <li>
    <router-link href="#" class="navs-item-mine" to="/">
      <img src="../../assets/images/menu-icon/navs-item-mine.png" alt="">
      <p>首页</p>
    </router-link>
  </li>
</ul>
</template>

<script>
export default {

}
</script>

<style>
.footer-nav{
  position: absolute;
  left:0;
  right:0;
  bottom:0;
  height:1rem;
  background-color: #F6F6F6;
}
.footer-nav li{
  float:left;
  height:1rem;
  line-height:1rem;
  width: 25%;
  position: relative;
  text-align:center;
}
a{
  display:block;
  text-align:center;

}
.footer-nav li a img{
  display:block;
  width: .5rem;
  height:.5rem;
  margin: 0 auto;
}
 .footer-nav li a p{
  font-size: .27rem;
  height:.5rem;
  line-height:.5rem;

}

</style>
<style>
.cart a{
  position: relative;
}
  .navs-bubble{
    background-color:#f40;
    color:#fff;
    line-height:.4rem;
    width:.4rem;
    text-align:center;
    font-size:.24rem;
    position:absolute;
    border-radius:50%;
    top:0;
    right:.7rem;
  }
  .cart.active{
    background:url('../../assets/images/menu-icon/navs-item-cart-active.png');
    background-repeat:no-repeat;
  }
</style>
