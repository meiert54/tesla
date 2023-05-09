<script setup lang="ts">
import { ref } from "vue";

interface ISectionProps {
    isModel: boolean,
    name: string,
    img: string,
    ncap: boolean
}

const props = defineProps<ISectionProps>()

const id = ref(props.isModel ? `model-${props.name.toLowerCase()}` : props.name.toLowerCase())
const title = ref(props.isModel ? `Model ${props.name.toUpperCase()}` : props.name.toUpperCase())
</script>

<template>
    <section :id="id" :style="{ backgroundImage: `url('/img/${img}')` }">
        <div class="title">
            <h1>{{ title }}</h1>
            <p>Réservez votre essai</p>
        </div>
        <div class="footer">
            <div class="buttons">
                <button>Découvrir nos véhicules disponibles</button>
                <button>Configuration personnalisée</button>
            </div>
            <p v-if="ncap">5 étoiles au crash-test Euro NCAP</p>
        </div>
    </section>
</template>