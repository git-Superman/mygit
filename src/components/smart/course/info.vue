<template>
<div>
    <main>
        <ul>
            <li v-for='i in 4' :key='i' class='list-item'>
                <img src="@/assets/img/xxxq-bimg.png" alt="">
                <div>
                    <p>怎样成为一个自律的人呢？</p>
                    <div class="item-div">
                        <img :src="isFalse" alt="">
                        <span>2019/12/20 15:00开课</span>
                    </div>
                    <div class='item-plan'>
                        <div>
                            <div>
                                <em :style='{width:plan+"%"}'></em>
                                <span>{{plan}}%</span>
                            </div>
                        </div>
                    </div>
                </div>
            </li>
        </ul>
    </main>
</div>
</template>
<script>
import isTrue from '@/assets/icon/class-zzsk.png'
import isFalse from '@/assets/icon/class-kksj.png'
export default {
    data(){
        return {
            isTrue,
            isFalse,
            week : ['一','二','三','四','五','六','日'],
            plan:50
        }
    }
}
</script>
<style lang="less" scoped>
main{
    ul{
        box-sizing: border-box;
        padding:0 .12rem .12rem .12rem;
        .list-item{
            display:flex;
            border-radius:.12rem;
            overflow: hidden;
            height:2.4rem;
            background-color:#fff;
            margin-bottom:.12rem;
            box-shadow: #000 1px 1px 5px -2px;
            >img{
                width:45%;height:100%;
            }
            >div{
                width:55%;
                box-sizing: border-box;
                padding:.2rem;
                color:#666;
                p{
                    height:1rem;
                    overflow: hidden;
                }
                .item-div{
                    display:flex;
                    align-items:center;
                    span{
                        font-size:.26rem;
                        color:#9E9E9E;
                    }
                    img{
                        width:.32rem;
                        height:.32rem;
                        margin-right:.12rem;
                    }
                }
                .item-plan{
                    display:flex;
                    justify-content: space-between;
                    margin-top:.2rem;
                    >div{
                        width:86%;height:.4rem;
                        border-radius:1rem 1rem;
                        text-align:center;
                        line-height: .4rem;
                        font-size:.28rem;
                        border:1px solid #009944;
                        overflow: hidden;
                        position:relative;
                        color:#fff;
                        padding:.02rem;
                        div{
                            width:100%;height: 100%;
                            position:relative;
                            box-sizing: border-box;
                            em{
                                content:'';
                                position:absolute;
                                left:0;
                                height:100%;
                                max-width:100%;
                                background-color:#009944;
                                border-top-left-radius:1rem;
                                border-bottom-left-radius:1rem;
                                border-top-right-radius:1rem;
                                border-bottom-right-radius:1rem;
                            }
                            span{
                                position: relative;
                                z-index: 2;
                                text-shadow: #009944 1px 1px 1px;
                            }
                        }
                    }
                }

            }
        }
    }
}
</style>