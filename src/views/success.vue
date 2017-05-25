<template>
    <section class="center">
        <i class="fa fa-check-circle-o"
           style="font-size: 50px;color: green;"></i><span style="font-size: 25px;color: green;">  提交成功！</span>
        <p style="color:#8391a5">{{num}} 秒后将自动跳转到问题单列表页</p>
    </section>
</template>

<script>
export default {
    data() {
        return {
            num: 5
        }
    },
    methods: {
        rerouter() {
            let interval = setInterval(() => {
                this.num--;
                if (this.num == 0) {
                    clearInterval(interval);
                    this.$router.push({ path: '/table' });
                }
            }, 1000);
        }
    },
    mounted() { this.rerouter() }

}

</script>

<style scoped>
.center {
    text-align: center;
    margin-top: 100px
}
</style>