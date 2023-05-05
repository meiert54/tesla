<script setup lang="ts">

</script>

<template>
    <div class="index-page">
        <section id="model-y">
            <div class="title">
                <h1>Model Y</h1>
                <p>Réservez votre essai</p>
            </div>
            <div class="footer">
                <div class="buttons">
                    <button>Découvrir nos véhicules disponibles</button>
                    <button>Configuration personnalisée</button>
                </div>
                <p>5 étoiles au crash-test Euro NCAP</p>
            </div>
        </section>
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
        padding-top: 9.7rem;
        padding-bottom: 1rem;
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
            gap: .5rem;

            h1 {
                font-size: 2.5rem;
            }

            p {
                font-size: .9rem;
                text-decoration: underline;
                text-underline-offset: .2rem;
            }
        }

        .footer {
            display: flex;
            flex-direction: column;
            gap: 2rem;

            .buttons {
                display: grid;
                grid-template-columns: repeat(2, 1fr);
                gap: 1.5rem;

                button {
                    padding: .7rem 1.5rem;
                    background: var(--font);
                    color: var(--white);
                    border: 0;
                    font-weight: bold;
                    font-size: .9rem;
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