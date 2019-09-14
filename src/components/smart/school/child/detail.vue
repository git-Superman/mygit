<template>
<div>
    <header>
        <div>
            <h5>小天才育林培训学校</h5>
            <span>
                成立于2015-01-15
            </span>
            <div>
                <img src="@/assets/icon/mian-rsicon.png" alt="">
                <span>157810</span>
            </div>
        </div>
        <div>
            <span>4.5分</span>
            <van-rate
                color='#4DBF68'
                :size="16"
                readonly
                v-model="value"
                allow-half
                void-icon="star"
                void-color="#eee"
                />
                <img class='sc' src="@/assets/icon/xxxq-sc.png" alt="">
        </div>
    </header>
    <main>
        <h5 class='title'>学校介绍</h5>
        <p class='main-item'>
            这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。这里是学校介绍，师资力量、开设课程、开创心路历程等等。
        </p>
    </main>
    <main>
        <h5 class='title'>老师介绍</h5>
        <ul class='list'>
            <li class='item-list' v-for="i in ser" :key='i'>
                <img src="@/assets/img/xxxq-lsface.png" alt="">
                <div>
                    <p>李鹏飞</p>
                    <span>
                        国家级情商讲师
                    </span>
                </div>
            </li>
            <li class='item-end' @click='handleClick'>
                <img :src="action ? isTrue : isFalse" alt="">
            </li>
        </ul>
    </main>

</div>
</template>
<script>
import isFalse from '@/assets/icon/kcjs-sqjt.png'
import isTrue from '@/assets/icon/kcjs-zkjt.png'
export default {
    data() {
        return {
            isFalse,
            isTrue,
            action : false,
            ser : 6,
            value:2.5
        }

    },
    methods:{
        handleClick(){
            if(!this.action){
                this.ser = 10;
                this.action = true;
            }else{
                this.ser = 5;
                this.action = false;
            }
        }
    }
}
</script>
<style lang="less" scoped>
header{
    font-size:.32rem;
    color:#666666;
    background-color:#fff;
    padding:.26rem;
    padding-right:0;
    margin-top:.06rem;
    display:flex;
    justify-content: space-between;
    position: relative;
    div:first-child{
        width:65%;
        box-sizing: border-box;
        color:#939292;
        h5{
            color:#666;
            font-size:.34rem;
            font-weight:600;
        }
        >span{
            font-size:.28rem;
        }
        div{
            display:flex;
            margin-top:.3rem;
            img{
                width:.5rem;
                height:.32rem;
            }
            span{
                color:#939292;
            }
        }
    }
    div:last-child{
        width:35%;
        text-align:center;
        span{
            color:#009944;
        }
        .sc{
            position:absolute;
            right:0;
            bottom:.26rem;
            width:1.7rem;
            height:.6rem;
        }
    }
}
main{
    box-sizing: border-box;
    padding:.2rem;
    margin-top:.12rem;
    background-color:#fff;
    font-size:.32rem;
    color:#666666;
    .title{
        color:#009944;
        font-weight: bold;
        font-size:.36rem;
        display:flex;
        align-items:center;
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
        display:flex;
        flex-wrap:wrap;
        justify-content: space-between;
        padding-bottom:.6rem;
        position:relative;
        .item-list{
            width:48%;
            display:flex;
            margin-top:.2rem;
            align-items: center;
            span{
                font-size:.24rem;
                color:#939292;
                max-height:.5rem;
                overflow: hidden;
            }
            img{
                width:1.2rem;
                height:1.2rem;
                border-radius:50%;
            }
        }
        .item-end{
            position:absolute;
            bottom:.3rem;left:50%;
            width:.36rem;
            height:.24rem;
            margin-left:-.18rem;
            img{
                width:100%;
                height:100%;
            }
        }
    }
    
}
</style>