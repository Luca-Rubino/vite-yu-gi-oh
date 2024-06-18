<script setup>

import axios from 'axios';

</script>

<script>

export default {
  // Properties returned from data() become reactive state
  // and will be exposed on `this`.
    data() {
        return {
            cards: [],
        }
    },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
    methods: {
        getApiYugioh() {
            // Make a request for a user with a given ID
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((response) => {
                // handle success
                console.log(response);
                this.cards = response.data.data
            })
            .catch((error) => {
                // handle error
                console.log(error);
            })
            .finally(() => {
                // always executed
            });
        }
    },
    created() {
        this.getApiYugioh()
    },

    // Lifecycle hooks are called at different stages
    // of a component's lifecycle.
    // This function will be called when the component is mounted.
    mounted() {
        console.log(this.cards.length)
    }
}
</script>

<template>

    <article>

        <aside>
            <div>
                <h2>Found {{ cards.length }} Cards</h2>
            </div>
            <div>
                <ul v-for="(cards, index) in cards" :key="index">
                    <li>
                        <img :src="cards.card_images[0].image_url" :alt="cards.name">
                    </li>
                    <li> {{ cards.name }} </li>
                    <li> {{ cards.archetype }} </li>
                </ul>
            </div>
        </aside>

    </article>

</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variants' as *;

aside{
    padding: 2.5rem;
    background-color: white;

    div{
        width: 100%;
        background-color: $color-white;

        h2{
            color: $color-white;
            background-color: $color-black;
            padding: 1rem;
            font-size: .7rem;
        }


    }

    div:nth-of-type(2) {
        @include d-flex;
        flex-wrap: wrap;
        justify-content: space-between;

        ul{
            width: calc((100% / 5) - 1rem);
            margin-bottom: 1rem;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            background-color: #d48f38;
            li {
                list-style: none;
                margin-bottom: .3rem;
                text-align: center;
                color: white;

                img{
                    width: -moz-available;
                }
            }

            li:nth-of-type(2) {
                text-transform: uppercase;
                font-size: .8rem;
                font-weight: 900;
            }
        }
    }
}
</style>