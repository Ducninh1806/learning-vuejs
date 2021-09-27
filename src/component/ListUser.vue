<template>
    <div class="list-user">
        <user class="user1"  v-for="user in listUser"
                v-bind:key="user.id" 
                v-bind:user="user"
                v-on:deleteUser = "handleDeleteUserInListUser"
        />
    </div>
</template>

<script>
import User from './User.vue'

export default {
  components: { User },
    name: 'list-user',
    props: {
        listUser: {
            type: Array        
        }
    },
    data(){
        return {

        }
    },
    methods: {
        handleDeleteUserInListUser(data){
            this.$emit('deleteUser',data);
            console.log(data)
        }
    },
    computed:{

    }
}
</script>

<style>
    .user1{
        position: relative;
        border: 1px solid teal;
        padding: 10px 15px;
        margin: 10px;
        width: 250px;
        height: 150px;
    }
</style>