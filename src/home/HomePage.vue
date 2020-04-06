<template>
    <div class="home">
        <div class="img-wrap">
            <img class="robot" src="../assets/robot-home.png" alt="home-robort">
        </div>
        <div class="get-started">
            <a href=""> Get Started </a> Building Your First Robot ! 
        </div>
    </div>
</template>


<script>
export default {
    name:'HomePage',
    data() {
        return {
            message: 'this is message'
        }
    },
}
</script>


<style>

    .home {
        text-align: center;
    }
    .robot {
        height:300px
    }
</style>


