<template>
<div>
    <nav-input @value='handleValue' test="搜索您想要的课程"></nav-input>
   <header>
        <van-swipe indicator-color='#71C99C' :duration='800' :autoplay="3000"  :loop="true" >
            <van-swipe-item>
                <img src="@/assets/img/dt-img2.png" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/dt-img2.png" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/dt-img2.png" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/dt-img2.png" alt="">
            </van-swipe-item>
        </van-swipe>
   </header>
    <nav-toop class='toop' @value="handleClick"></nav-toop>
    <div class="content">
        <div @click="handleClickPush" v-for='i in 8' :key='i'>
            <img src="@/assets/img/wdsc-kcimg.png" alt="">
            <div class='content-item'>
                <p>怎样成为一个自律的人呢？</p>
                <p>
                    <img src="@/assets/icon/mian-rsicon.png" alt="">
                    <span>157810</span>
                </p>
            </div>
        </div>
    </div>
</div>
</template>
<script>
import navInput from '@/components/global/nav-input'
import navToop from '@/components/global/nav-toop'
export default {
    data(){
        return {
            value : ''
        }
    },
    methods:{
        handleValue(val){
            console.log(val)
        },
        handleClick(va,a){
            console.log(va,a)
        },
        handleClickPush(){
            this.$router.push('/smart/details');
        }
    },
    created(){
        var swiper = this.$refs.swiper;
    
    },
    components:{
        navInput,
        navToop
    }
}
</script>
<style lang="less" scoped>
/deep/.van-swipe{
    padding:.26rem 0 !important;
    .van-swipe-item{
        img{
            width:100%;
            // height:180px;
        }
    }
    .van-swipe__indicators{
        bottom:0;
    }
    .van-swipe__indicator{
        background-color:#666;
        border-radius:1rem 1rem;
    }
    .van-swipe__indicator--active{
        width:.36rem;
    }
}
.toop{
    margin-top:.2rem;
}

.content{
    display:flex;
    flex-wrap: wrap;
    color:#666666;
    font-size:.28rem;
    >div{
        width:46%;
        border-radius:.2rem;
        overflow: hidden;
        margin:.2rem 0 0 .2rem;
        >img{
            width:100%;height:2.6rem;
        }
        .content-item{
            background-color:#fff;
            box-sizing: border-box;
            padding:.18rem;
            p:first-child{
                max-height:.8rem;
                overflow: hidden;
                margin-bottom:.12rem;
            }
            p:last-child{
                img{
                    width:.5rem;height:.32rem;
                }
                span{
                    vertical-align: text-bottom;
                    font-size:.26rem;
                }
            }
        }
    }
    
}
</style>