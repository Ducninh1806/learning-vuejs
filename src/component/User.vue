<template>
    <div class="user">
        <p>{{user.email}}</p>
        <button class="delete1" v-on:click="handleDeleteUser">Delete</button>
    </div>
</template>

<script>
export default {
    name: "user",
    props: {
        user: Object,
        default: null
    },
    data() {
        return {
            textUser: "Hello User"
        }
    },
    computed: {

    },
    methods:{
        handleDeleteUser(e) {
            this.$emit("deleteUser", this.user);
        }
    }

}
</script>

<style>
    .user {
        position: relative;
    }
    .delete1 {
         position: absolute;
         top: 0;
         right: 0;
    }
</style>