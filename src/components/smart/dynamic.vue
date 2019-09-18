<template>
<div>
    <header>
        <nav-input class='input' :test="test"></nav-input>
        <img class='sctp' @click='show = true' src="@/assets/icon/dt-sctp.png" alt="">
    </header>
    <main>
        <div class="content">
        <div @click="handleClickPush" v-for='(item,i) in list' :key='i'>
            <img :src="item.img" alt="">
            <div>
                <div class='content-t'>
                    <img src="@/assets/img/dt-face.png" alt="">
                    <div>
                        <p>你的眼yey</p>
                        <span>{{item.time}}</span>
                    </div>
                </div>
                <div class='content-item'>
                    <p>{{item.test}}</p>
                    <p>
                        <img :src="isTrue" alt="">
                        <span>{{item.value}}</span>
                    </p>
                </div>
            </div>
        </div>
    </div>
    </main>
    <van-overlay
        class='overlay'
        :show="show"
        @click="show = false"
        />
    <footer :style="!show ? 'height:0' : 'height:4.2rem'" class='foot-alert-img'>
        <van-uploader capture='camera' multiple>
            <img src="@/assets/icon/scdt-pz.png" alt="">
            <span>拍照</span>
        </van-uploader>
        <van-uploader multiple>
            <img src="@/assets/icon/scdt-xc.png" alt="">
            <span>从相册中选取</span>
        </van-uploader>
        <div @click='show = false'>
            <p>取消</p>
        </div>
    </footer>
</div>
</template>
<script>
import navInput from '@/components/global/nav-input'
import isTrue from '@/assets/icon/dt-ydz.png'
import isFalse from '@/assets/icon/dt-wdz.png'
export default {
    data() {
        return {
            isTrue,
            isFalse,
            test : '搜索您想了解的话题..',
            show : false,
            list : [
                {
                    img : require('@/assets/img/dt-img.png'),
                    test : '换个发型',
                    time : '09-26 14:30',
                    value : 78
                },
                {
                    img : require('@/assets/img/dt-img.png'),
                    test : '换个心情。',
                    time : '09-26 14:30',
                    value : 35
                },
                {
                    img : require('@/assets/img/dt-img.png'),
                    test : '换个发型，换个心情！',
                    time : '09-26 14:30',
                    value : 12
                }
            ]
        }
    },
    methods:{
        handleClickPush(){
            this.$router.push('/smart/smartDynamicEditor');
        }
    },
    components:{
        navInput
    }
}
</script>
<style lang="less" scoped>
/deep/.van-uploader__input-wrapper{
    width:100%;
    text-align:center;
}
header{
    display:flex;
    background-color:#fff;
    .input{
        width:100%;
    }
    .sctp{
        width:.6rem;height:.5rem;
        padding:.26rem .3rem .26rem .1rem;
        flex-shrink: 0;
    }
}
main{
    .content{
        display:flex;
        flex-wrap: wrap;
        color:#666666;
        font-size:.32rem;
        >div{
            width:46%;
            border-radius:.2rem;
            overflow: hidden;
            margin:.2rem 0 0 .2rem;
            background-color:#fff;
            >img{
                width:100%;
            }
             .content-t{
                 display:flex;
                 align-items:center;
                 margin-top:.12rem;
                 padding-left:.12rem;
                 img{
                     width:.7rem;
                     height:.7rem;
                     flex-shrink:0;
                     border-radius:50%;
                     margin-right:.2rem;
                 }
                 div{
                     font-size:.28rem;
                     p{
                        width: 100%;
                        white-space:nowrap;
                        text-overflow: ellipsis;
                        overflow: hidden;
                     }
                     span{
                         font-size:.24rem;
                     }
                 }
             }
            .content-item{
                background-color:#fff;
                box-sizing: border-box;
                padding:.12rem;
                font-size:.28rem;
                p:first-child{
                    max-height:.8rem;
                    overflow: hidden;
                    margin-bottom:.12rem;
                }
                p:last-child{
                    float: right;
                    img{
                        width:.32rem;height:.28rem;
                    }
                    span{
                        vertical-align: text-bottom;
                        font-size:.26rem;
                        color:#22AC39;
                    }
                }
            }
            .content-item::after{
                content:'';
                display:block;
                clear: both;
            }
        }
        
    }
}
/deep/.overlay{
    z-index:98 !important;
}
.foot-alert-img{
    position:fixed;
    bottom:0;
    z-index:99;
    background-color:transparent;
    width:100%;
    transition:height .5s;
    div{
        width:100%;
        margin-top:.16rem;
        padding:.26rem 0;
        font-size:.36rem;
        background-color:#fff;
        text-align:center;
        color:#666666;
        img{
            width:.6rem;
            height:.5rem;
            margin-right:.12rem;
        }
        span{
            vertical-align: middle;
        }
    }
    div:last-child{
        background-color:#E4E4E4;
    }
}
</style>