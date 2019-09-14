<template>
<div>
    <nav-input test='搜索您想了解的学校'></nav-input>
    <nav-toop class='toop'></nav-toop>
    <main>
        <ul>
            <li @click="handleClickPush" v-for='(item,i) in 5' :key='i' class='list-item'>
                <div class='a'>
                    <img class='a' src="@/assets/img/wdsc-xximg.png" alt="">
                </div>
                <div class='b'>
                    <h5>小天才育林培训学校</h5>
                    <div class='grade'>
                        <p>综合类</p>
                        <van-rate
                        color='#4DBF68'
                        :size="18"
                        readonly
                        v-model="value"
                        allow-half
                        void-icon="star"
                        void-color="#eee"
                        />
                    </div>
                    <div class='subject'>
                        <p>小学数学</p>
                        <p>小学英语</p>
                        <p>小学奥数</p>
                        <p>小学语文</p>
                    </div>
                </div>
                <img class='c' src="@/assets/icon/wd-jrjt.png" alt="">
            </li>
        </ul>
    </main>
</div>
</template>
<script>
import navInput from '@/components/global/nav-input'
import navToop from '@/components/global/nav-toop'
import isTrue from '@/assets/icon/school-star-yx.png'
import isFalse from '@/assets/icon/school-star-wx.png'
export default {
    data() {
        return {
            isTrue,
            isFalse,
            value : 4.5,
            gradeIcon : [
                {
                    action : true
                },
                {
                    action : true
                },
                {
                    action : true
                },
                {
                    action : true
                },
                {
                    action : false
                },
            ]
        }
    },
    methods:{
        handleClickPush(){
            this.$router.push('/smart/schoolDetails/detail');
        }
    },
    components:{
        navInput,
        navToop
    }
}
</script>
<style lang="less" scoped>
.toop{
    margin-top:.08rem;
}
main{
    font-size:.32rem;
    color:#666;
    box-sizing: border-box;
    padding:.12rem;
    .list-item{
        background-color:#fff;
        border-radius:.2rem;
        overflow: hidden;
        display:flex;
        align-items:center;
        margin-top:.08rem;
        width:100%;
        height:2.2rem;
        div.a{
            width:38%;height:100%;
            img{
                width:100%;height:100%;
            }
        }
        div.b{
            width:57%;
            box-sizing: border-box;
            padding:.16rem 0 .16rem .2rem;
            font-size:.28rem;
            h5{
                font-size:.32rem;
                font-weight:600;
            }
            .grade{
                display:flex;
                color:#9E9E9E;
                margin:.12rem;
                align-items:center;
                p{
                    margin-right:.12rem;
                }
            }
            .subject{
                display:flex;
                flex-wrap: wrap;
                margin-top:.12rem;
                p{
                    width:50%;
                    display:flex;
                    align-items:center;
                }
                p::before{
                    content:'';
                    display:inline-block;
                    width:.08rem;height:.08rem;
                    border-radius:50%;
                    background-color:#666;
                    margin-right:.12rem;
                }
            }
        }
        img.c{
            width:.2rem;
        }
    }
}
</style>