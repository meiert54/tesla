<script setup lang="ts">

</script>

<template>
    <main class="index-page">
        <ModelSection id="model-y" title="Model Y" :ncap="true" />
        <ModelSection id="model-3" title="Model 3" :ncap="true" />
        <ModelSection id="model-s" title="Model S" :ncap="false" />
        <ModelSection id="model-x" title="Model X" :ncap="false" />
        <section id="powerwall"></section>
        <section id="accessoires"></section>
    </main>
</template>

<style lang="scss">
.index-page {
    scroll-behavior: smooth;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
    width: 100%;
    height: 100vh;

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