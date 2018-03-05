<!--looping over quotes
which are in the parent - app.vue
placing the quote data inside-->
<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    // import the quote component
    // set props so it can be passed to parent (app.vue) and quote data can be accessed there
    // set the component name


    import Quote from './Quote.vue';

    export default {
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }

</script>

<style>

</style>