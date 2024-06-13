<script setup>

</script>

<template>

<header>
    <section>

        <article>
            <img src="../assets/img/Yu-Gi-Oh_Logo.png" alt="Yu-Gi-Oh_Logo" >
        </article>

        <article>
            <h1>Yu-Gi-Oh Api</h1>
        </article>

    </section>
</header>

</template>

<style lang="scss" scoped>

@use '../styles/partials/mixin' as *;
@use '../styles/partials/variants' as *;

section{
    @include d-flex;
    flex-direction: row;
}

article:first-of-type{
    justify-content: flex-end;
    width: calc(100% - 90%);
}

article{
    @include d-flex;
    align-items: center;
    justify-content: flex-start;

    h1{
    font-size: 2rem;
    font-weight: 100;
    }

    img{
        background-color: $color-white;
        width: 69px;
        margin-right: 1rem;
    }
}

</style>
