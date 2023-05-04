<script setup lang="ts">
interface IHeaderEmits {
    (e: 'openMenu'): void
}

const emit = defineEmits<IHeaderEmits>()

const openMenu = () => emit('openMenu')
</script>

<template>
    <header>
        <div class="logo">
            <img src="/img/logo.png" alt="logo">
        </div>
        <ul>
            <li class="item">Model S</li>
            <li class="item">Model 3</li>
            <li class="item">Model X</li>
            <li class="item">Model Y</li>
            <li class="item">Powerwall</li>
            <li class="item">Recharge</li>
        </ul>
        <ul>
            <li class="item">Assistance</li>
            <li class="item">Shop</li>
            <li class="item">Compte</li>
            <li @click="openMenu" class="item">Menu</li>
        </ul>
    </header>
</template>

<style lang="scss">
header {
    position: fixed;
    padding: .5rem 1.5rem;
    width: 100%;
    display: flex;
    justify-content: space-between;

    .logo {
        cursor: pointer;
        width: 150px;

        img {
            width: 100%;
            height: 100%;
        }
    }

    ul {
        list-style: none;
        display: flex;
        align-items: center;
        
        .item {
            cursor: pointer;
            padding: .5rem 1rem;
            border-radius: .2rem;
            font-size: .9rem;
            font-weight: bold;
            color: var(--font);

            &:hover {
                background: var(--hover);
            }
        }
    }
}
</style>