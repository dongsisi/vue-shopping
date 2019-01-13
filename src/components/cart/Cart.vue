<template>
<div class="cart">
  <Header></Header>
  <div class="scroll">
    <div class="block">
      <table>
        <tbody>
          <tr>
             <th width="28%">收
               <span class="ui-hidden"></span>
               货<span class="ui-hidden"></span>人
              </th>
              <td>一个狗蛋儿 先生</td>
              <td width="17%" rowspan="3" class="more">修改</td>
          </tr>
          <tr>
            <th>电 <span class="ui-hidden"></span>话</th>
            <td>153********</td>
          </tr>
          <tr>
            <th>收货地址</th>
              <td style="font-weight: 700">上海市浦东新区航头镇航都路18号-黑马程序员</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="main-con">
      <div class="fast">
        <span class="fast-supper">闪送超市</span>
        <span class="addbtn">凑单专区</span>
      </div>
      <p class="price-txt theme-border">￥0起送，22点后满￥69运费5元起，不满￥69运10元起</p>
      <p class="group-receive theme-border">
        收货时间
        <span class="ext"> 可预定</span>
        <span class="time">08:00-09:00</span>
      </p>
      <div class="group-comment theme-border">
        收货备注
        <div class="comment-wrapper">
          <input type="text" placeholder="可输入100字以内特殊要求内容">
        </div>
      </div>
      <table class="group-list theme-border">
        <tbody>
          <td class="checkbox active"></td>
          <td style="width:1.1rem">
           <div class="item-img-wrap">
              <div class="item-img">
                <img src="../../assets/images/1.jpg" alt="">
            </div>
           </div>
          </td>
          <td class="product">
            <div class="item-txt">银鹭桂圆八宝</div>
            <div class="item-price">￥5.00</div>
            <div class="product-operates">
              <span>
                <span class="product-operates-item  del">
                  <span class="inner"></span>
                </span>
                <span class="product-operates-item amount">1</span>
              </span>

              <span class="product-operates-item add">
                <span class="inner"></span>
              </span>
            </div>
          </td>
        </tbody>
      </table>
      <div class="settlement">
        <span class="selectAll selectAll-false selectAll-true">全选</span>
        共:
        <span class="theme-price">￥0</span>
        <div class="chose">选好了</div>
      </div>

    </div>
  </div>
  <Footer></Footer>
</div>
</template>

<script>
import Header from '../common/Header'
import Footer from '../common/Footer'
export default {
  data(){
    return{

    }

  },

   components: {
    Header,
    Footer
  }
}
</script>
<style>
    .scroll{
      position: absolute;
      top:1.33rem;
      right:0;
      left:0;
      bottom:1rem;
      background-color:#efefef;
    }
    .block{
      background-color: #fff;
      margin: .3rem 0;
      display: block;
      background-image: url('../../assets/images/place.png');
      background-repeat: repeat;
      background-position: left top, left bottom;
      background-size: auto 0.1rem;
      padding: .05rem 0;
    }
    table{
      width:100%;
      background-color: white;
      border-collapse: collapse;
      border-spacing: 0;
    }
    table th{
      padding: .2rem .2rem .2rem .5rem;
      font-weight:400;
      font-size:.28rem;
      text-align:left;
      vertical-align: baseline;
    }
    table td{
      font-size:.26rem;
      padding: .2rem 0;
    }
    .more{
      background:url('../../assets/images/more.png');
      background-repeat: no-repeat;
      background-position:right center;
      background-size:.58rem auto;
      padding-right:.32rem;
    }

</style>
<style>
  .main-con{
    padding-top:.3rem;
    background-color: #fff;
  }
  .fast-supper{
    display:inline-block;
    height:.4rem;
    color:#999;
    font-size:.16rem;
    padding-left:.45rem;
    background-size:.3rem;
    line-height:.4rem;
  }
  .fast{
    position: relative;
  }
  .fast-supper::before{
    background-color:#ffd600;
    content:'';
    display:inline-block;
    width:.07rem;
    height:.4rem;
    vertical-align:-0.1rem;
    border-radius:.2rem;
    margin-right:.13rem;
  }
  .addbtn{
    position: absolute;
    top:0;
    right:.24rem;
    width:1.4rem;
    height:.42rem;
    line-height:.42rem;
    border-radius:.2rem;
    color:#e64f1a;
    font-size:.19rem;
    border-style:solid;
    text-align:center;
    border-width:.02rem;
  }
  .price-txt{
    font-size:.3rem;
    line-height:.8rem;
    color:#999;
    padding-left:.4rem;
    white-space:nowrap;
    text-overflow:ellipse;
    overflow:hidden;
  }
  .theme-border{
    border-bottom:.01rem solid #c0c0c0;
  }
  .group-receive{
    position:relative;
    padding-left:.4rem;
    height: .8rem;
    line-height:.8rem;
    background:url('../../assets/images/more.png');
    background-repeat: no-repeat;
    background-position:right center;
    background-size:.58rem auto;
    padding-right:.36rem;
  }
  p{
    font-size:.3rem;
    color:#333;
  }
  p .ext{
    float:right;
    padding-right:.47rem;
  }
  p .time{
    color:#e64f1a;
    padding-left:.4rem;
  }
  .group-comment{
    position:relative;
    padding-left:.4rem;
    height: .8rem;
    line-height:.8rem;
    font-size:.3rem;
  }
  .comment-wrapper{
    position: absolute;
    left:2rem;
    top:0;
    bottom:0;
    right:.5rem;
  }
  .comment-wrapper input{
    width:100%;
    height:.5rem;
    border:1px solid #cecece;
    text-indent: .2rem;
    border-radius:.2rem;
    font-size:.22rem;
  }
  .group-list{
    line-height:.6rem;
    /* background-color: pink; */
  }
  .group-list .checkbox{
    background:url("../../assets/images/check.png");
    background-size: .43rem .43rem;
    background-position: center;
    background-repeat:no-repeat;
    width: 1.07rem;
    height:1.07rem;
  }
  .group-list .checkbox.active{
    background:url('../../assets/images/checked.png');
    background-size: .43rem .43rem;
    background-position: center;
    background-repeat:no-repeat;
    width: 1.07rem;
    height:1.07rem;
  }
  .group-list tr td{
    position:relative;
    font-size:.24rem;
    padding: 0;
  }
  .item-img-wrap{
     width: .8rem;
    height:.8rem;
  }
  .item-img-wrap img{
   width: .8rem;
    height:.8rem;
  }
  .item-txt{
    line-height:.5rem;
    white-space:nowrap;
    text-overflow:ellipse;
    overflow: hidden;
  }
  .product-operates{
    position:absolute;
    width:1.8rem;
    height:1rem;
    line-height:.93rem;
    right: .27rem;
    bottom:0;
    text-align:center;
    border-radius: .13rem;
    color:#f40;
  }
  .product-operates-item{
    box-sizing:border-box;
    position:absolute;
    height:100%;
    line-height:.93rem;
    top:0;
  }
  .product{
    position: relative;
  }
  .product-operates .add{
    right:0;
    width: .13rem;
    z-index: 2;
  }
  .product-operates-item.add .inner{
    background-position:right center;
  }
  .product-operates-item.del .inner{
    background-position:left center;
  }
  .product-operates-item .inner{
    position:absolute;
    top:.15rem;
    right:0;
    width:.5rem;
    height:.5rem;
    background: #ff4300 url('../../assets/images/jia.png');
    background-size:200% 100%;
    border-radius:50%;
    border-width: 1px;
    border-style:solid;
    border-color:#ffbe89;
  }
  .product-operates-item .del{
    left:0;
    width: .13rem;
    z-index: 2;
  }
  .product-operates .amount{
    font-size:.28rem;
    line-height:.5rem;
    color:#333;
    top:.15rem;
    left:1rem;


  }
  .settlement{
    padding-left:.3rem;
    height:1rem;
    line-height:1rem;
    font-size:.21rem;
  }
  .selectAll{
    display:inline-block;
    min-width: .4rem;
    padding-left:1rem;
    background-size: .43rem .43rem;
    background-repeat:no-repeat;
    background-position:left center;
    font-size: .26rem;
    padding-right:.3rem;

  }
  .selectAll-true{
    background-image:url('../../assets/images/checked.png');
  }
  .theme-price{
    color:#e64f1a;
    font-size:.26rem;
  }
  .chose{
    background-color:#ffd600;
    float:right;
    width: 1.6rem;
    text-align:center;
    font-size:.34rem;
  }



</style>
