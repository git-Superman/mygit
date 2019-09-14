<template>
<div>
     <main>
         <ul v-for="(item,i) in icon" :key='i' class='item-list'>
             <li class='list-title'>
                 <h5>第{{i+1}}节课</h5>
                 <span>2019/12/20 15:00-16:00</span>
             </li>
             <li>怎样成为一个自律的人</li>
             <li class='list-content' :style="item.action ? 'height:auto' : 'height:0'">
                 课程介绍：Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo similique corrupti aliquid voluptatem autem perferendis, praesentium ipsa dolorem labore eius?
             </li>
             <li class='list-active'>
                 <img :src="!item.action ? isTrue : isFalse" @click="item.action = !item.action" alt="">
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
            icon:[
                {
                    action:true
                },
                {
                    action:false
                },
                {
                    action:false
                },
                {
                    action:false
                },
            ]
        }
    }
}
</script>
<style lang="less" scoped>
main{
    font-size:.32rem;
    color:#666;
    .item-list{
        background-color:#fff;
        box-sizing: border-box;
        padding:.2rem;
        margin-top:.06rem;
    }
    .list-title{
        color:#22AC39;
        display: flex;
        justify-content: space-between;
        margin-bottom:.1rem;
        span{
            color:#9E9E9E;
        }
    }
    .list-content{
        overflow: hidden;
        margin-top:.12rem;
        transition:all 1s;
    }
    .list-active{
        img{
            display:block;
            width:.36rem;
            margin:0 auto;
            padding:.2rem;
        }
    }
}
</style>