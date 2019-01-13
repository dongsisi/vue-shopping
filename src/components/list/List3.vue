<template>
  <div class="list">
    <Header></Header>
    <div class="list-content">
      <!-- 左侧菜单 -->
      <div class="left-menu"  ref="menuWrapper">
        <ul class="ul">
          <li v-for="(menu ,i) in categories" :key="menu.id"  @click="selectMenu(i, menu.id)"><span @click="demo" :class="{ news: !menu.icon, active: selectedIndex === i }">{{menu.name}}</span>
          </li>
        </ul>
     </div>
      <!-- 右侧内容 -->
      <div class="con">
        <div class="nav">
          <li>全部分类</li>
          <li>综合排序</li>
        </div>
        <!-- 主产品区 -->
        <div class="product" ref="foodsWrapper">
          <ul>
            <li v-for="item in selectedProductions" :key="item.id" >
              <div class="menu-img" @click="getInfo(item.id)">
                <img :src="item.img" alt="" width="55" height="55">
              </div>
              <div class="pro-txt" @click="getInfo(item.id)">
                <h4>{{item.name}}</h4>

                <p class="list1">{{ item.specifics }}</p>
                <p class="list2">
                  <b>￥{{ item.price }}</b>
                  <i v-if="item.price !== item.market_price">￥{{item.market_price}}</i>
                </p>
              </div>
              <div class="pro-circle">
                <span class="pro-item del">
                  <span class="inner"></span>
                  <span class="amount">1</span>
                </span>
                <span class=" pro-item add">
                  <span class="inner"></span>
                </span>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from '../common/Header'
import Footer from '../common/Footer'
import axios from 'axios'
import '@/tools/index.js'
import '@/store/index.js'
import BScroll from 'better-scroll'
export default {
  created(){
    this.getAsideList()
  },

data(){
  return{
    categories:[],
    products:[],
    selectedProductions: [],
    //记录高亮菜单的索引号
    selectedIndex:0
  }
},
methods:{
  demo(){
    console.log(1);
  },
  //区域滚动
  initScroll(){
          //初始化需要滚动的对象,通过vm.$refs可以获取到在<template>中设置ref=menuWrapper属性的元素节点
          this.menuScroll = new BScroll(this.$refs.menuWrapper,{
            scroll:true,
            click:true
          });
          this.foodsScroll = new BScroll(this.$refs.foodsWrapper,{
            scroll:true,
            click:true
          });
        },
  getAsideList(){
    this.$http.jsonp('http://localhost:3008/list').then(res=>{
      console.log(res)
    const {categories,products} = res.data
    this.categories = categories
    this.products = products
    this.selectedProductions = products[categories[0].id].map(item =>{
      return {
        ...item,
      }
    })
    this.$nextTick(()=>{
        this.initScroll()
      })
      })
  },
  //切换左侧菜单
  selectMenu(index,id){
    console.log(1);
    this.selectedIndex = index
    console.log(this.selectedIndex)
      this.selectedProductions = this.products[id].map(item => {
        return {
          ...item,
      }
    })
  },

  getInfo(id){
    this.$router.push(`/goodsinfo/${id}`)
  }
},
 components: {
    Header,
    Footer,
  },

}
</script>
<style >
html,
body{
  height:100%;
}
#app{
  min-width: 320px;
}
.list{
  /* position: absolute; */
  /* left:0; */
  /* right:0; */
  /* height:10.8rem; */
  background: #fff;
  min-width: 320px;
  height: 100%;
  padding-top: 1.33rem;
  padding-bottom: 1rem;
  box-sizing: border-box;
}
.list-content{
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  /* top:1.33rem;
  bottom:1rem; */
  background: #ffffff;
}
.left-menu{
  width: 1.8rem;
  flex: 0 0 1.8rem;
  height:8.5rem;
  background-color:#F8F8F8;
  overflow: hidden;
}
.con{
  /* width:100%; */
  flex:1;
  /* height: 100%; */
}
.left-menu li{
  height: 1.1rem;
  line-height:1.1rem;
  text-align:center;
  border-bottom:1px solid #ccc;
  box-sizing: border-box;
}
.left-menu li span{
  font-size: .3rem;
}
.left-menu .active{
  border-left:2px solid yellow;
}
.left-menu li{
position: relative;
}
.left-menu span{
  display:block;
}
.left-menu .news::after{
  position: absolute;
  top:0;
  right:0;
  content:'';
  background-image: url('../../assets/images/new.jpg') ;
  width:.68rem;
  height:.68rem;
  background-size:100%;
}

.con .nav{
  width:100%;
  height:.8rem;
  line-height: .8rem;
  /* background-color: yellowgreen; */
  text-align: center;
}
.nav li{
  float:left;
  font-size: .28rem;
  width:50%;
}

</style>
<style>
.product{
  width:100%;
  height: 100%;
  overflow: hidden;
  /* background-color: #f5f5f5; */
}
.product li{
  /* border-bottom:1px solid #ccc; */
  border-top:1px solid #ccc;
  height: 2.28rem;
  padding-bottom: .11rem;
  margin-bottom:.27rem;
  position: relative;
}
.pro-img{
  margin-left:10px;
  margin-top:.67rem;
  background-size:cover;
  float:left;
}
.pro-img img{
  width:.98rem;
  height: .98rem;
  vertical-align: middle;
  border: 0;
}
.pro-txt{
 margin:-1.0rem .5rem .5rem 1.5rem;
}
.pro-txt h4{
  font-size: .34rem;
  font-weight:400;
  margin-top: .13rem;
  margin-bottom:.13rem;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}
.pro-txt p{
  font-size: .28rem;
  line-height: .34rem;
  vertical-align: bottom;
}
.pro-txt .list1{
  color:#ccc;
  line-height:.44rem;
}
.pro-txt .list2 b{
  color:#f00;
}
.pro-txt .list2 i{
  color:#999999;
 text-decoration: line-through;
 font-style:normal;
}
.pro-circle{
  position: absolute;
  width: 2.5rem;
  height:1.8rem;
  line-height:1.5rem;
  right:.36rem;
  bottom:0;
}
.add{
  right: 0;
  width: .4rem;
  z-index: 10;
 box-sizing: border-box;
 position: relative;
 height: 100%;
 top: 0;
}
.pro-item .inner{
    position: absolute;
    top: .85rem;
    left: 0.8rem;
    width: .6rem;
    height: .6rem;
    background:#ff4300  url('../../assets/images/jia.png');
    background-size:200% 100%;
    border-radius: 50%;
    color: #ff4300;
    border-style:solid;
    border-color: #ffbe89;
    border-width:.01rem;
}
.del .inner{
    position: absolute;
    top: .85rem;
    left: 1.8rem;
    width: .6rem;
    height: .6rem;
    background:#ff4300  url('../../assets/images/jia.png')right center;
    background-size:200% 100%;
    border-radius: 50%;
    color: #ff4300;
    border-style:solid;
    border-color: #ffbe89;
    border-width:.01rem;
}
.amount{
  position: absolute;
  right:.8rem;
  bottom:-.07rem;
  font-size:.28rem;
}


</style>
