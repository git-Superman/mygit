<template>
<div>
     <main>
         <ul class='list'>
             <li @click='handleClickPush' v-for="i in 6" :key='i' class="item-list">
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

export default {
    data() {
        return {
            
        }
    },
    methods:{
        handleClickPush(){
            this.$router.push('/smart/details/evaluate');
        }
    }
}
</script>
<style lang="less" scoped>
main{
    font-size:.32rem;
    color:#666;
    .list{
        // 
        box-sizing: border-box;
        padding:.16rem;
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