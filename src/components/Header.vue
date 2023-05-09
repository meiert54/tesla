<script setup lang="ts">
import { ref, computed } from "vue";

interface IHeaderEmits {
    (e: 'openMenu'): void
}

const emit = defineEmits<IHeaderEmits>()

const indicatorOpacity = ref(0)
const indicatorWidth = ref(0)
const indicatorLeft = ref(0)

const indicatorStyle = computed(() => {
    return {
        opacity: indicatorOpacity.value,
        width: indicatorWidth.value + 'px',
        left: indicatorLeft.value + 'px'
    }
})

const hover = (e: MouseEvent) => {
    let el: any = e.target

    indicatorWidth.value = el.offsetWidth
    indicatorLeft.value = el.offsetLeft

    setTimeout(() => indicatorOpacity.value = .6, 50)
}

const leave = () => setTimeout(() => indicatorOpacity.value = 0, 50)

const openMenu = () => emit('openMenu')
</script>

<template>
    <header>
        <div class="logo">
            <div class="icon">
                <svg class="tds-icon tds-icon-logo-wordmark tds-site-logo-icon" viewBox="0 0 342 35" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 .1a9.7 9.7 0 0 0 7 7h11l.5.1v27.6h6.8V7.3L26 7h11a9.8 9.8 0 0 0 7-7H0zm238.6 0h-6.8v34.8H263a9.7 9.7 0 0 0 6-6.8h-30.3V0zm-52.3 6.8c3.6-1 6.6-3.8 7.4-6.9l-38.1.1v20.6h31.1v7.2h-24.4a13.6 13.6 0 0 0-8.7 7h39.9v-21h-31.2v-7h24zm116.2 28h6.7v-14h24.6v14h6.7v-21h-38zM85.3 7h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 13.8h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zm0 14.1h26a9.6 9.6 0 0 0 7.1-7H78.3a9.6 9.6 0 0 0 7 7zM308.5 7h26a9.6 9.6 0 0 0 7-7h-40a9.6 9.6 0 0 0 7 7z" fill="currentColor"></path>
                </svg>
            </div>
        </div>
        <ul>
            <li @mouseover="hover" @mouseleave="leave" class="item">Model S</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Model 3</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Model X</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Model Y</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Powerwall</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Recharge</li>
        </ul>
        <ul>
            <li @mouseover="hover" @mouseleave="leave" class="item">Assistance</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Shop</li>
            <li @mouseover="hover" @mouseleave="leave" class="item">Compte</li>
            <li @mouseover="hover" @mouseleave="leave" @click="openMenu" class="item">Menu</li>
        </ul>
        <span :style="indicatorStyle" class="indicator"></span>
    </header>
</template>