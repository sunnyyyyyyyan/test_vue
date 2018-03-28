<template>
  <div class="hello">
    <div class="container">
      <h2>购物车</h2>
      <div class="header">
        <ul>
          <li>商品信息</li>
          <li>商品金额</li>
          <li>商品数量</li>
          <li>总金额</li>
          <li>编辑</li>
        </ul>
      </div>

      <hr>
      <div class="content">
        <ul >
          <li class="content-item">
            <div class="content-item-list">
              <img src="../assets/img/forever-1.jpg" alt="永生花-1">
              <dl>
                <dt>赠送:</dt>
                <dd>束带</dd>
                <dd>盒子</dd>
              </dl>
            </div>
          </li>
          <li>
            ￥18
          </li>
          <li>
            <input type="text" placeholder="-">
            1
            <input type="text" placeholder="+">
          </li>
          <li>￥18</li>
          <li>删除</li>
        </ul>
        <ul>
          <li class="content-item">
            <div class="content-item-list">
              <img src="../assets/img/forever-2.jpg" alt="永生花-1">
              <dl>
                <dt>赠送:</dt>
                <dd>束带</dd>
                <dd>盒子</dd>
              </dl>
            </div>
          </li>
          <li>
            ￥18
          </li>
          <li>
            <input type="text" placeholder="-">
            1
            <input type="text" placeholder="+">
          </li>
          <li>￥18</li>
          <li>删除</li>
        </ul>

      </div>

      <div class="footer">
        <div class="footer-left">
          <div class="footer-left-all">
            <a>全选</a>
          </div>
          <div class="footer-right-noall">
            <a>取消全选</a>
          </div>
        </div>

        <div class="footer-right">
          <div class="footer-right-totalMoney">
            <span>totalMoney:</span>
          </div>
          <div class="footer-right-getCount">
            <button>结算</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      productList:[]
    }
  },
  methods:{
    cartView(){
      let _this = this;
      this.$http.get("data/cartData.json",{"id":123}).then(function(res){
        this.productList = res.body.result.list;
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .header{
    margin-top: 30px;
    height: 40px;
  }
  ul{
    display: block;
    list-style: none;
  }
  li{
    float: left;
    width: 220px;
  }
  .content-item{

  }

  .content-item img{
    width: 100px;
    height: 100px;
  }
  li input{
    text-align: center;
    width: 20px;
    height: 20px;
  }
  .footer{
    position: fixed;
    bottom: 50px;
  }
  .footer-left{
    float: left;
  }
  .footer-left-all{
    float: left;
    margin-left: 30px;
  }
  .footer-right-noall{
    float: right;
    margin-left: 5px;
  }
  .footer-right{
    float: right;
  }
  .footer-right-totalMoney{
    float: left;
  }
  .footer-right-getCount{
    float: right;
  }

</style>
