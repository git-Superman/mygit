<template>
    <div>
        <header>
            <div>
                <p v-for='(item,i) in week' :key='i' v-html='item'></p>
            </div>
            <div>
                <p v-for='i in 7' :class='i == 4 ? "action" : ""'  :key='i'><span v-html='i+10'></span></p>
            </div>
        </header>
        <main>
            <ul>
                <li v-for='i in 4' :key='i' class='list-item'>
                    <img src="@/assets/img/xxxq-bimg.png" alt="">
                    <div>
                        <p>怎样成为一个自律的人呢？</p>
                        <div>
                            <img :src="isFalse" alt="">
                            <span>2019/12/20 15:00开课</span>
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
            week : ['一','二','三','四','五','六','日']
        }
    }
}
</script>
<style lang="less" scoped>
header{
    background-color:#fff;
    padding-bottom:.2rem;
    div{
        display:flex;
        justify-content: space-between;
        p{
            width:14.3%;
            text-align:center;
            padding:.3rem 0;
            color:#9E9E9E;
        }
    }
    div:last-child{
        p{
            color:#666;
            position:relative;
            z-index:1;
        }
        span::before{
            content:'';
            display:block;
            width:.6rem;height:.6rem;
            position: absolute;
            top:50%;right:50%;
            margin-top:-0.3rem;
            margin-right:-0.31rem;
            background-color:transparent;
            border-radius:50%;
            z-index:-1;
        }
        p.action{
            span{
                color:#fff;
            }
            span::before{
                background-color:#71C99C;
            }
        }
    }
}
main{
    ul{
        box-sizing: border-box;
        padding:.12rem;
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
                    height:1.6rem;
                    overflow: hidden;
                }
                div{
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
            }
        }
    }
}
</style>