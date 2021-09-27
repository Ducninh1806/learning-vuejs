<template>
    <div class="demoRef">
        <h1>Hello Demo REF</h1>
        <button class="avatar" v-on:click= "handleInputFile">Thay đổi avatar</button>
        <input type="file" ref="styleAvatar" style="display: none">
    </div>

</template>

<script>
export default {
    name: 'DemoRef',
    data () {
        return {

        }
    },
    methods :{
        handleInputFile(e){
            this.$refs.styleAvatar.click();
            console.log(this.$refs);
        }
    }
}
</script>
<style>
    .demoRef {
        padding: 250px;
        margin: auto;
        border: 1px solid rgb(0, 0, 0);
    }
    .avatar {
        color: rgb(255, 255, 255);
        border: 2px solid #333;
        padding: 10px 15px;
        background-color: #333;
        transition: all .3s ease;
    }
    .avatar :hover {
        color: #333;
        background-color: #fff;
    }
</style>