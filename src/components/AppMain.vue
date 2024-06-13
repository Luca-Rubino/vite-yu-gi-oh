<script>

</script>

<template>

<main>
    <section>

        <article>
            <select name="" id="genereCard">
                <option value="Alien">Alien</option>
            </select>
        </article>

        <article>
            <h2>La mia lista card</h2>
        </article>
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
    width: calc(100% - 20%);
}

select{
    margin: 1rem 1rem 1rem 1.5rem;
    padding: .5rem 5rem .5rem .5rem;
    background-color: $color-white;
    border: 0;
    border-radius: 5px;
}

</style>
