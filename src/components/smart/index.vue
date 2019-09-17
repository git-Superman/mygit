<template>
<div>
    <nav-input @value='handleValue' test="搜索您想要的课程"></nav-input>
   <header>
        <van-swipe indicator-color='#71C99C' :duration='800' :autoplay="3000"  :loop="true" >
            <van-swipe-item>
                <img src="@/assets/img/qq1.jpg" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/qq2.jpg" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/qq3.jpg" alt="">
            </van-swipe-item>
            <van-swipe-item>
                <img src="@/assets/img/qq4.jpg" alt="">
            </van-swipe-item>
        </van-swipe>
   </header>
    <nav-toop class='toop' @value="handleClick"></nav-toop>
    <div class="content">
        <div @click="handleClickPush(item)" v-for='(item,i) in list' :key='i'>
            <img :src="item.img" alt="">
            <div class='content-item'>
                <p>{{item.test}}</p>
                <p>
                    <img src="@/assets/icon/mian-rsicon.png" alt="">
                    <span>{{item.value}}</span>
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
            value : '',
            list:[
                {
                    test:'语言智能 Language',
                    img:require('@/assets/img/qq1.jpg'),
                    value:2862,
                    cont:'体听说读写的能力，个人能顺利而高效地利用语言描述事件，表达思想并与人交流的能力'
                },
                {
                    test:'音乐智能 Music',
                    img:require('@/assets/img/qq2.jpg'),
                    value:8331,
                    cont:'个人感受、辨别、记忆、改变和表达音乐的能力，个人对节奏、音调和旋律的敏感以及通过作曲、演奏和歌唱等表达自己思想能力'
                },
                {
                    test:'逻辑数学智能 Math',
                    img:require('@/assets/img/qq3.jpg'),
                    value:12642,
                    cont:'个体运算和推理的能力，能够将物体量化，对命题和假设，进行思考和推理，并进行复杂的数学运算等'
                },
                {
                    test:'音乐智能 Art',
                    img:require('@/assets/img/qq4.jpg'),
                    value:57395,
                    cont:'利用视觉信息和三维空间的方式进行思维的能力'
                },
                {
                    test:'身体智能 TPR',
                    img:require('@/assets/img/qq5.jpg'),
                    value:2862,
                    cont:'灵活的操纵物体，调整身体的能力'
                },
                {
                    test:'自然观察智能 Science',
                    img:require('@/assets/img/qq6.jpg'),
                    value:8331,
                    cont:'善于观察自然界中的各种形态，对物体进行辨认和分类，洞察自然的能力；'
                },
                {
                    test:'人际关系智能 Social',
                    img:require('@/assets/img/qq7.jpg'),
                    value:12642,
                    cont:'个体与人相处与交往的能力，个人觉察、体验他人情绪、情感和意图并据此作出适宜反应的能力'
                },
                {
                    test:'内省智能 Speech',
                    img:require('@/assets/img/qq8.jpg'),
                    value:12642,
                    cont:'意识到自己的心理活动以及原因，理解他人的思想、情绪和情感，依据对自己的认识及对他人的理解指导自己的行为'
                }
            ]
        }
    },
    methods:{
        handleValue(val){
            console.log(val)
        },
        handleClick(va,a){
            console.log(va,a)
        },
        handleClickPush(e){
            this.$router.push({path:'/smart/details',query:e});
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
            width:100%;height:2rem;
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