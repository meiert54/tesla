<script setup lang="ts">

</script>

<template>
    <div class="index-page">
        <section id="model-y"></section>
        <section id="model-3"></section>
        <section id="model-s"></section>
        <section id="model-x"></section>
        <section id="powerwall"></section>
        <section id="accessoires"></section>
    </div>
</template>

<style lang="scss">
.index-page {
    scroll-behavior: smooth;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
    width: 100%;
    height: 100vh;

    section {
        scroll-snap-align: center;
        height: 100vh;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    #model-y {
        background-image: url('/img/model-y.png');
    }

    #model-3 {
        background-image: url('/img/model-3.png');
    }
    
    #model-s {
        background-image: url('/img/model-s.png');
    }
    
    #model-x {
        background-image: url('/img/model-x.png');
    }
    
    #powerwall {
        background-image: url('/img/powerwall.png');
    }
    
    #accessoires {
        background-image: url('/img/accessoires.png');
    }
}
</style>