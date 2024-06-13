<script>

</script>

<template>

<main>
    <section class="d-flex">

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
main{
    height: 69rem;
    background-color: #d48f38;
}

section{
    flex-direction: column;
    align-items: center;
}

article{
    width: calc(100% - 15%);
}

select{
    margin: 1rem;
    padding: .5rem 5rem .5rem .5rem;
    background-color: white;
    border: 0;
    border-radius: 5px;
}
</style>
