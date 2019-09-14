<template>
<div>
    <nav-bar :test='test'></nav-bar>
    <header>
        <div class="month">
            <p v-for='(item,i) in dayList' :key='i' :class="i == month ? 'action' : '' "  @click="handleDay(i)" v-html='item'></p>
        </div>
        <div class='sky'>
            <div>
                <p v-for='(item,i) in week' :key='i' v-html='item'></p>
            </div>
            <div>
                <!-- <p v-show='y!=7' v-for='s of y' :key='s' v-html='y'></p>
                 -->
                <p :style='{minWidth:y}'></p>
                <p v-for='i in dates' :class='i == day ? "action" : ""' :key='i'><span v-html='i'></span></p>
            </div>
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
import navBar from '@/components/global/navBar'
import isTrue from '@/assets/icon/class-zzsk.png'
import isFalse from '@/assets/icon/class-kksj.png'
export default {
    data() {
        return {
            test : '课程日历',
            dayList : ['一月','二月','三月','四月','五月','六月','七月','八月','九月','十月','十一月','十二月'],
            month : Number,
            dates : Number,
            day : Number,
            y : '',
            week : ['一','二','三','四','五','六','日'],
            isTrue,
            isFalse
        }
    },
    created(){
        var myDate = new Date();
        // 获取当前月份
        this.month = myDate.getMonth();
        // 获取当前月份天数
        this.day = myDate.getDate();
        var year = myDate.getFullYear();
        var d = new Date(year,this.month + 1,0);
        this.dates = d.getDate();
        // 获取当前星期
        var y = myDate.getDay();
        this.y = (7 - y) * 14.2 +'%';
        console.log(this.y);
    },
    methods:{
        handleDay(i){
            this.day = 0;
            this.month = i;
            var myDate = new Date();
            var year = myDate.getFullYear();
            // 获取当前月份
            var month = myDate.getMonth();
            // 获取当前月天数数
            var day = myDate.getDate();
            i == month ? this.day=day : '';
            var d = new Date(year,i+1,0);
            this.dates = d.getDate();
            
        }
    },
    components:{
        navBar
    }
}
</script>
<style lang="less" scoped>
header{
    width:100%;
    margin-top:.06rem;
    .month{
        overflow-x:auto;
        -webkit-overflow-scrolling:touch;
        display:flex;
        background-color:#fff;
        margin-bottom:.06rem;
        width:100%;
        p{
            min-width:1.5rem;
            padding:.3rem 0;
            color:#666666;
            text-align:center;
        }
        p.action{
            background-color:#71C99C;
            color:#fff;
        }
    }
    .month::-webkit-scrollbar {
        display: none;
    }
    .sky{
        background-color:#fff;
        padding-bottom:.2rem;
        div{
            display:flex;
            p{
                width:14.2%;
                text-align:center;
                padding:.26rem 0;
                color:#9E9E9E;
            }
        }
        div:last-child{
            width:100%;
            flex-wrap: wrap;
            p{
                color:#666;
            }
            p.a span::after{
                background-color:#F39800;
            }
            p.action{
                color:#fff;
                span::before{
                    background-color:#71C99C;
                }
            }

            span{
                position:relative;
                z-index:2;
            }
            span::after,span::before{
                content:'';
                position:absolute;
                width:.1rem;height:.1rem;
                top:50%;
                left:50%;
                margin-top:0.4rem;
                margin-left:-.05rem;
                background-color:transparent;
                border-radius:50%;
            }
            span:before{
                width:.6rem;height:.6rem;
                background-color:transparent;
                margin-left:-0.3rem;
                margin-top:-0.3rem;
                z-index:-1;
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