<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" v-bind:key="index" @click.native="deleteQuote(index)"> {{ quote }} </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote';

    export default {
        props: ['quotes'],
        components: {
            appQuote: Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', this.index);
            }
        }
    }
</script>

<style>

</style>