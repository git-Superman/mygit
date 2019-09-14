<template>
<div>
    <nav-bar :test='test'></nav-bar>
    <div class="content">
        <img class='t' src="@/assets/img/wdsc-lsimg.png" alt="">
        <h5>李茶的</h5>
        <p>国家特级情商讲师</p>
        <span>这里是老师简介，这里是老师简介，这里是老师简介，这里是老师简介，这里是老师简介，这里是老师简介，这里是老师简介。</span>
        <img class='float' src="@/assets/icon/lsxq-scicon.png" alt="">
    </div>
    <main>
        <h5 class='title'>课程介绍</h5>
         <ul class='list'>
             <li v-for="i in 6" :key='i' class="item-list">
                 <img src="@/assets/img/wdsc-kcimg.png" alt="">
                 <div>
                     <p>怎样成为一个自律的人呢?</p>
                     <span>¥999.99</span>
                 </div>
             </li>
         </ul>
     </main>
</div>
</template>
<script>
import navBar from '@/components/global/navBar'
export default {
    data() {
        return {
            test : '老师详情',
            height : 'height:0;',
            action : false,
            show : true
        }
    },
    methods:{
        
    },
    components:{
        navBar
    }
}
</script>
<style lang="less" scoped>
.content{
    position:relative;
    background-color:#fff;
    margin-top:.12rem;
    box-sizing: border-box;
    padding:.2rem;
    img.t{
        display:block;
        width:2rem;height:2rem;
        border-radius:50%;
        margin:0 auto;
    }
    h5,p{
        text-align:center;
        color:#666666;
    }
    h5{
        font-size:.36rem;
        font-weight:bold;
        color:#50A278;
        margin:.08rem 0;
    }
    span{
        margin-top:.2rem;
        display:block;
        color:#9E9E9E;
    }
    img.float{
        position: absolute;
        right:0.2rem;top:0.2rem;
        width:.62rem;
    }
}
main{
    font-size:.32rem;
    color:#666;
    .title{
        color:#009944;
        font-weight: bold;
        font-size:.36rem;
        display:flex;
        align-items:center;
        background-color:#fff;
        box-sizing: border-box;
        padding:.1rem .12rem;
        margin-top:.12rem;
    }
    .title::before{
        content:'';
        display: inline-block;
        width:.12rem;
        height:.42rem;
        background-color:#009944;
        border-radius:50rem 50rem;
        margin-right:.2rem;
    }
    .list{
        // 
        box-sizing: border-box;
        padding:0 .16rem .16rem .16rem;
        .item-list{
            margin-top:.1rem;
            background-color:#fff;
            border-radius:.2rem;
            overflow: hidden;
            height:2.4rem;
            display:flex;
            box-shadow: #000 .02rem .02rem .08rem -.02rem;
            img{
                width:50%;
                height:100%;
            }
            div{
                width: 50%;height:100%;
                box-sizing: border-box;
                padding:.2rem;
                p{
                    height:1.5rem;
                    overflow: hidden;
                }
                span{
                    font-size:.36rem;
                    color:#FE6B0D;
                    font-weight:bold;
                }
            }
        }
    }

}
</style>