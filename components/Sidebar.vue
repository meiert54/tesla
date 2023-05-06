<script setup lang="ts">
interface ISidebarProps {
    active: Boolean
}

interface ISidebarEmits {
    (e: 'closeMenu'): void
}

const props = defineProps<ISidebarProps>()
const emit = defineEmits<ISidebarEmits>()

const closeMenu = () => emit('closeMenu')
</script>

<template>
    <nav :class="{ active: active }" class="sidebar">
        <div class="header">
            <div @click="closeMenu" class="xmark">
                <font-awesome-icon :icon="['fas', 'xmark']" />
            </div>
        </div>
        <ul class="navigation">
            <li class="nav-item">Model S</li>
            <li class="nav-item">Model 3</li>
            <li class="nav-item">Model X</li>
            <li class="nav-item">Model Y</li>
            <li class="nav-item">Véhicules disponibles</li>
            <li class="nav-item">Véhicules D'occasion</li>
            <li class="nav-item">Reprise</li>
            <li class="nav-item">Essais</li>
            <li class="nav-item">Véhicules de société</li>
            <li class="nav-item">Powerwall</li>
            <li class="nav-item">Énergie</li>
            <li class="nav-item">Électricité pour les professionnels</li>
            <li class="nav-item">Industries</li>
            <li class="nav-item">Recharge</li>
            <li class="nav-item">Nous trouver</li>
            <li class="nav-item">Assistance</li>
            <li class="nav-item">Relations investisseurs</li>
            <li class="nav-item">Compte</li>
            <li class="nav-item">Cybertruck</li>
            <li class="nav-item">Roadster</li>
            <li class="nav-item">Actualités</li>
            <li class="nav-item">Événements</li>
        </ul>
    </nav>
</template>

<style lang="scss">
.sidebar {
    position: fixed;
    padding: 2rem 1rem;
    background: var(--white);
    height: 100vh;
    right: 0;
    transform: translateX(100%);
    transition: transform .3s ease;

    &.active {
        transform: translateX(0);
    }

    .header {
        margin-bottom: 2rem;
        display: flex;
        justify-content: flex-end;

        .xmark {
            padding: .3rem .6rem;
            font-size: 1.7rem;
            color: var(--font);
            cursor: pointer;
            border-radius: .2rem;
            transition: background .3s ease;

            &:hover {
                background: var(--hover);
            }
        }
    }

    .navigation {
        padding: 0 1rem;
        list-style: none;
        display: flex;
        flex-direction: column;
        gap: .5rem;

        .nav-item {
            cursor: pointer;
            padding: .5rem;
            border-radius: .2rem;
            font-size: .9rem;
            font-weight: bold;
            letter-spacing: -0.3px;
            color: var(--font);
            transition: background .3s ease;

            &:hover {
                background: var(--hover);
            }
        }
    }
}
</style>