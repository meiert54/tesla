<script setup lang="ts">
interface ISectionProps {
    id: string,
    title: string,
    ncap: boolean
}

const props = defineProps<ISectionProps>()
</script>

<template>
    <section :id="id">
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

<style lang="scss">
section {
    padding-top: 7rem;
    padding-bottom: 0;
    scroll-snap-align: center;
    height: 100vh;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;

    .title {
        text-align: center;
        color: var(--font);
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: .5rem;

        h1 {
            font-size: 2.5rem;
            letter-spacing: -0.5px;
        }

        p {
            cursor: pointer;
            position: relative;
            letter-spacing: -0.3px;
            padding-bottom: 1px;
            font-size: .9rem;
            
            &::before {
                content: '';
                position: absolute;
                left: 0;
                bottom: 0;
                height: 1.3px;
                width: 100%;
                background: #000;
                transform: scaleY(1);
                transform-origin: top;
                transition: transform .3s ease;
            }

            &:hover::before {
                transform: scaleY(1.3);
            }
        }
    }

    .footer {
        display: grid;
        grid-template-rows: repeat(2, 1fr);
        gap: 2rem;

        .buttons {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;

            button {
                cursor: pointer;
                padding: .7rem 1.5rem;
                background: var(--font);
                color: var(--white);
                border: 0;
                font-weight: bold;
                font-size: .9rem;
                letter-spacing: -0.3px;
                border-radius: .3rem;

                &:nth-child(2) {
                    background: var(--white);
                    color: var(--font);
                }
            }
        }

        p {
            text-align: center;
            font-size: .75rem;
        }
    }
}
</style>