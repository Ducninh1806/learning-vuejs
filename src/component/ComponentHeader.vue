<template>
    <header>
        <h1>
            {{titleHeader}}
        </h1>
        <button v-on:click="changeTitle">Thay đổi title tại ComponentHeader</button>
    </header>
</template>
<script>
export default {
    name: "comp-header",
    props:{
        titleHeader: String,
    },
    data () {
        return {
            text: "Header"
        }
    },
    methods: {
        changeTitle(e) {
            console.log("trước khi kích hoạt")
            var data = {
                title: "test => data thông qua biến event"
            }
            this.$emit('changeTitleEvent', data)
            console.log("sau khi kích hoạt")

        }
    }
}
</script>

<style>

</style>