<template>
    <footer><h1>{{titleFooter}}</h1></footer>

</template>

<script>
export default {
    name: "comp-footer",
    props: {
        titleFooter: String,
    },
    data () {
        return {
            textFooter: "Footer"
        }
    }
}
</script>

<style>

</style>