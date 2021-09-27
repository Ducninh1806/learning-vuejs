<template>
  <div id="app">
    <button v-on:click="title = 'học lập trình Vuejs'">thay đổi title từ component App.vue</button>

    <component-header v-bind:titleHeader="title" v-on:changeTitleEvent="handleChangeTitle"/>
    <div class="">
    <list-user v-bind:listUser="listUserD" v-on:deleteUser="handleDeleteUserInApp"/>
    </div>
    <demo-ref />
    <demo-slot/>
    

    <div class="row">
      <div class="column" style="background-color:#aaa;">
        <h2>Column 1</h2>
        <p>Some text..</p>
      </div>
      <div class="column1" style="background-color:#bbb;">
        <div>
          <button v-on:click="handleColapse(1)">Menu 1</button>
          <div v-if="isColapse === 1"> COlap 1</div>
          <button v-on:click="handleColapse(2)">Menu 2</button>
                    <div v-if="isColapse === 2"> COlap 2</div>

          <button v-on:click="handleColapse(3)">Menu 3</button>
                    <div v-if="isColapse === 3"> COlap 1</div>
        </div>
      </div>
      
    </div>

    <table>
  <tr>
    <th>id</th>
    <th>Email</th>
    <th>active</th>
  </tr>
  <tr v-for="(user, index) in listUserD" v-bind:key="index">
    <td>{{user.id}}</td>
    <td>{{user.email}}</td>
    <td>{{user.active}}</td>
  </tr>

</table>
      
    <component-footer v-bind:titleFooter="title" />
  </div>
</template>

<script>
import ComponentHeader from './component/ComponentHeader.vue';
import ComponentFooter from './component/ComponentFooter.vue';
import ListUser from './component/ListUser.vue';
import DemoRef from './component/DemoRef.vue';
import DemoSlot from './component/DemoSlot.vue'

export default {
  components: { ComponentHeader, ComponentFooter, ListUser, DemoRef, DemoSlot},
  name: 'app',
  data () {
    return {
      title: "Hello Vuejs header component cha",
      msg: 'Hello world',
      listUserD: [
        { id: 1, email: "test1@gmail.com", active: true},
        { id: 2, email: "test2@gmail.com", active: false},
        { id: 3, email: "test3@gmail.com", active: true},
        { id: 4, email: "test4@gmail.com", active: true},
        { id: 5, email: "test5@gmail.com", active: true},
        { id: 6, email: "test6@gmail.com", active: false},
        { id: 7, email: "test7@gmail.com", active: true},
        { id: 8, email: "test8@gmail.com", active: true},
        { id: 9, email: "test9@gmail.com", active: true}
        ],
        isColapse: 0
    }
  },
  methods: {
    handleChangeTitle(data){
      this.title= data.title;
      console.log("handleChangeTitle được gọi sau khi kich hoạt thành công tại App.vuew")
    },
    handleDeleteUserInApp(data){
        console.log("console.log tại App", data)
        this.listUserD = this.listUserD.filter(function( obj ) {
            return obj.id !== data.id;
        });
    },
     handleColapse(e) {
      console.log(e, this),
      this.isColapse = e;
    }
  },
  computed: {
   
  },

  // end method
  beforeCreate() {
      console.log("beforeCreate", this.title)
    },

    //call API hoặc call AJAX để lấy data
    created() {
      console.log("Created", this.title)
    },

    beforeMount(){
      console.log("beforeMount", this.title)

    },

    mounted(){
      // nếu muốn sử dụng được Jquery, chỉ truy xuất được DOM trong mounted -> có thể sử dụng Jquery
      console.log("mounted", this.title)

    },

    beforeUpdate(){
      console.log("beforeUpdate", this.title)

    },

    updated(){
      console.log("updated", this.title)

    },

    beforeDestroy(){
      console.log("beforeDestroy", this.title)

    },
    destroyed(){
      console.log("destroyed", this.title)

    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}


* {
  box-sizing: border-box;
}

/* Create three equal columns that floats next to each other */
.column {
  float: left;
  width: 33.33%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Create three equal columns that floats next to each other */
.column1 {
  float: left;
  width: 66.67%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
