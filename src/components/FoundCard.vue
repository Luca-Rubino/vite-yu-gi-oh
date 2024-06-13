<script>

</script>

<template>

    <article>

        <aside>
            <div>
                <h2>Found 39 Cards</h2>
                <span></span>
            </div>
        </aside>

    </article>

</template>

<style lang="scss" scoped>
@use '../styles/partials/mixin' as *;
@use '../styles/partials/variants' as *;

aside{
    div{
        background-color: $color-white;
        padding: 2.5rem 2.5rem 0 2.5rem;

        h2{
            color: $color-white;
            background-color: $color-black;
            padding: 1rem;
            font-size: .7rem;
        }

        span{
            display: block;
            height: 42.8em;
            margin-bottom: 1rem;
            background-color: red;
        }
    }
}

</style>