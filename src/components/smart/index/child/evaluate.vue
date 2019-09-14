<template>
<div>
    <main>
        <ul>
            <li v-for='i in 5' :key='i' class='list-items'>
                <img src="@/assets/img/wd-face.png" alt="">
                <div>
                    <h5>学生小AA</h5>
                    <span>2019/12/20 15:00</span>
                    <p>
                        课程非常好，老师也很棒！通俗易懂，值得推荐。
                    </p>
                </div>
            </li>
        </ul>
    </main>
</div>
</template>
<style lang="less" scoped>
main{
    font-size:.32rem;
    color:#666;
    .list-items{
        display:flex;
        background-color:#fff;
        margin-top:.06rem;
        box-sizing: border-box;
        padding:.2rem;
        >img{
            display:block;
            min-width:1.2rem;
            min-height:1.2rem;
            max-width:1.2rem;
            max-height:1.2rem;
            border-radius:50%;
            margin-right:.2rem;
            flex-shrink:0;
        }
        div{
            h5{
                color:#22AC39;
            }
            span{
                display:block;
                margin:.1rem 0 .16rem;
                color:#9E9E9E;
                font-size:.28rem;
            }
        }
    }
}
</style>
