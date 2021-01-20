<template>
  <div class="hello">
    <div id="content">
       <div id="left">
        <pre id="code" ref="code">{{ code }}</pre>
           
       </div>
       <div id="right">
       <pre id="mine" ref="mine">{{ mine }}</pre>
         
       </div>
        <div id="whale">
          <div class="main">
            <div class="disc1"></div>
            <div class="disc2"></div>
            <div class="square"></div>
          </div>
        </div>
    </div>
   <div v-html="styleCode"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      code:``,
      codeStyle:`
      *{
        transition: all .1s;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }
      *::after{
        box-sizing: border-box;
      }
      *::before{
        box-sizing: border-box;
      }
      /* 加3D效果 */
      html{
        perspective: 1000px;
      }
      #content{
        height:100vh;
        margin:0;
      }
      .hello{
        width:100%;
        height:100%
      }
      #code{
        overflow: auto;
        height: 100%;
      }
      #left{
        text-align: left;
        font-size: 16px;
        position: absolute;
        left: 112px;
        top: 72px;
        border: 5px solid #2897a4;
        background: #000;
        color:#D88162;
        width: 57rem;
        height: 678px;
        -webkit-transform: rotateY(14deg) translateZ(-146px);
        transform: rotateY(14deg) translateZ(-146px);
        display: inline-block;
      }
      html {
        color: #fff; background: rgb(0,64,64);
      }
      #mine{
        overflow: auto;
        height: 100%;
      }
      #right{
        text-align: left;
        font-size: 18px;
        color: #fff;
        display: inline-block;
        margin-top: 73px;
        position: absolute;
        width: 57rem;
        height: 678px;
        border: 5px solid #2897a4;
        background: #000;
        -webkit-transform: rotateY(-14deg) translateZ(-146px);
        transform: rotateY(-14deg) translateZ(-146px);
      }
      /* 换个颜色*/
      #mine{
        color:#000;
      }
      #right{
        background: #ccc;
      }
      /*画个心吧*/
      #whale{
        width: 100%;
        height: 330px;
        /*border: 1px solid green;*/
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
        align-items: center;
        /*background: #c3bfc3;*/
        position: absolute;
        bottom: 28px;
        transform: rotateX(22deg) translateZ(-92px);
      }
      .disc1{
        width: 100px;
        height: 100px;
        border:1px solid red;
        background-color: red;
        margin:100px 0px 0px 100px;
        border-radius:100%;
        float:left;
      }
      .disc2 {
        width: 100px;
        height: 100px;
        border: 1px solid red;
        background-color: red;
        margin: 50px 2px 0px 0px;
        border-radius: 100%; 
        float: left;
        position: relative;
        right: 50px;
      }
      .square{
        width: 100px;
        height: 100px;
        border:1px solid red;
        background-color: red;
        margin: 100px 0px 0px 0px;
        float: left;
        position: relative;
        right: 152px;
      
      }
      .main{
        transform: rotate(45deg);
        margin-left: 138px;
      }
            `,
      mine:``,
      mineCode:`
        个人资料
        ====

        坐标：北京
        年龄：26
        工作年限：4年
        学历：本科
        专业：软件开发
        电子邮件：qlysurprise@163.com

        求职意向
        ====

        工作性质：全职
        目标地点：北京
        目标职位：web前端工程师
        薪资：面议
        求职状态：可随时入职
       
        专业技能
        ====
        
        1. 熟练掌握HTML、css 等前端技术的应用开发
        2. 熟练使用响应式框架：Bootstrap；类库：Jquery、zepto.js等
        3. 熟练使用插件slide.js,fullpage.js,Echars,swiper4,UI组件：mui,mint-ui,element-ui,layui等
        4. 可以使用vue进行项目开发，理解Vue全家桶（vue,cue-router,axios,vuex）以及相关的使用方式
        5. 熟悉html5和css3，熟练使用部分常用语法；熟练掌握原生Javascript,DOM等前端技术
        6. 熟悉less预编译技术，熟练掌握flex布局、流式布局、响应式布局、rem布局等布局方式，
           按照需求利用合适的布局方式进行pc和移动端的开发
        7. 熟练使用ajax技术以及模板引擎与后台进行数据的交互，实现异步通信以及数据的渲染和页面局部刷新功能
        8. 熟练前端构建工具webpack、svn以及包管理工具npm，熟练使用git进行代码管理项目
        9. 了解node.js和数据库mysql;PHP的基础语法和基本API
       10. 熟练开发微信公众号，了解小程序开发       

        工作经历
        ----

        1. 潍坊乐多收科技有限公司(2016.7-2018)
        2. 北京一雄信息科技有限公司(2018.3-至今)

        项目
        ----
        1. 微信公众号：车匠在线
        2. 车匠在线后台管理系统
        3. 爱课博（http://www.aikebo.cn/）
        4. 盛世和安网站（http://shengshihean.com/）
        5. 小程序：策划宝典、和安课件
        6. 乐多收内部管理系统
        7. 五谷杂粮APP
        8. 吃过没（pc+移动端）
        9. 喜购物（电商）
        10. 潍坊美食网（pc端）
        `,
    }
    
  },
  created(){
      let n = 0;
      let time = setInterval(() => {
        this.code = this.codeStyle.substring(0,n);
        n += 1
          code.scrollTop = 100000
        if( n >= 1423){
          window.clearInterval(time);
             this.nineCodeFn()
        }
       },10);
       
      // this.code = this.codeStyle
    },
    methods: {
      nineCodeFn(){
           let m = 0;
            let timem = setInterval(() => {
              this.mine = this.mineCode.substring(0,m)
              m += 1
                mine.scrollTop = 100000
              if( m >= this.mineCode.length){
                window.clearInterval(timem);

                let p = 1424;
                let timeb = setInterval(() => {
                  this.code = this.codeStyle.substring(0,p)
                  p += 1
                   code.scrollTop = 100000
                  if( p >= this.codeStyle.length){
                    window.clearInterval(timeb);

                    }
                 },10);
              }
            },1)
      }
    },
    computed:{
      styleCode(){
         return '<style>' + this.code +'</style>'
      }
     
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
    html{
      font-size:16px;
    }
</style>
