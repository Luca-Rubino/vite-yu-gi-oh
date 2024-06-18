<script setup>

import axios from 'axios';
import FoundCard from '../components/FoundCard.vue';

</script>

<script>

    export default {
        data() {
            return {
                cards: [],
                archetypes: [],
                selectedArchetype: '',
            }
        },
        methods: {
            getApiYugioh() {
                // Make a request for a user with a given ID
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
                .then((response) => {
                    // handle success
                    this.cards = response.data.data
                })
                .catch((error) => {
                    // handle error
                    console.log(error);
                })
                .finally(() => {
                    // always executed
                });
            },
            getArchetypes(){
                axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then((response) => {
                    this.archetypes=response.data;
                })
                .catch(function(error){
                    console.log(error);
                })
                .finally(function(){
                });
            },
            handleChange (event) {
                console.log(event)
                this.selectedArchetype=event;
                // // value è valore che seleziona utente nella select
                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${this.selectedArchetype}`)
                .then((response) => {
                    this.cards=response.data.data;
                    console.log(this.selectedArchetype)
                })
                .catch(function(error){
                    console.log(error);
                })
                .finally(function(){
                });
            },
            created() {
                this.getApiYugioh()
                this.getArchetypes();
            },
        },
        mounted() {
            this.getArchetypes();
            this.getApiYugioh();
        }
    }

</script>

<template>

<main>
    <section>

        <article>
            <select name="archetype" id="archetype" v-model="selectedArchetype" @change="handleChange(selectedArchetype)">
                <option v-for="(archetype, index) in archetypes" :key="index" :value="archetype.archetype_name">
                    {{ archetype.archetype_name }}
                </option>
            </select>
        </article>

    </section>

    <section>
        <FoundCard :cards="cards" :selectedArchetype="selectedArchetype"></FoundCard>
    </section>
    
</main>

</template>

<style lang="scss" scoped>

@use '../styles/partials/mixin' as *;
@use '../styles/partials/variants' as *;

main{
    background-color: $color-bg-body;
}

section{
    @include d-flex;
    flex-direction: column;
    align-items: center;
}

article{
    width: calc(100% - 21.4%);
}

select{
    margin: 1rem 1rem 1rem 1.5rem;
    padding: .5rem 5rem .5rem .5rem;
    background-color: $color-white;
    border: 0;
    border-radius: 5px;
}

</style>
