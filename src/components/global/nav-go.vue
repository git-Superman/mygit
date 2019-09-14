<template>
<div>
    <div class='fixed' @click='handleClickPush'>
        <img src="@/assets/icon/kcjs-return.png" alt="">
    </div>
</div>
</template>
<script>
export default {
    data() {
        return {

        }
    },
    methods:{
        handleClickPush(){
            this.$router.go(-1);
        }
    }
}
</script>
<style lang="less" scoped>
.fixed{
    height:.8rem;
    width:100%;
    position: fixed;
    top:0;
    background-color:rgba(0,0,0,.6);
    img{
        width: 0.28rem;
        height: 0.42rem;
        position: absolute;
        left: 0.2rem;
        top: 50%;
        margin-top: -0.21rem;
    }
}
</style>