<template>

  <div>

    <div v-bind="sortData(userData)">
      <h1>User rating</h1>
      <Btt v-on:changeSort="chngSrt =! chngSrt"/>
    </div>
    

    <UserID
      v-on:click="$emit('changeSort')"
      v-for="user in userData"
      :key="user.point"
      :user="user"
    />

  </div>

</template>

<script>

import UserID from "./UserID";
import Btt from "./Btt";
import axios from 'axios';

export default {
  name: "DataTabs",
  components: {
    UserID, Btt
  },
  data: function() {
    return {
      chngSrt: false,
      userData: []
    };
  },
  
  created() {
      axios.get("https://my-json-server.typicode.com/Vespand/crmm-tasks/users/")
        .then(response => {
          
          this.userData = response.data;

          for (let j = 0; j < this.userData.length ; j++){
            this.userData[j].num = j;}
            
          return this.userData;
        })
        .catch(e => { this.errors.push(e) })
      },

  methods: {
    sortData: function() {     
    
    var chng = this.chngSrt;
    var user0 = this.userData;
  
      for (let j = user0.length - 1; j > 0; j--) {
        for (let i = 0; i < j; i++) {
          if ( (user0[i].rating < user0[i + 1].rating) === chng ) {
            let temp = user0[i];
            this.userData[i].num = i;
            user0[i] = user0[i + 1];
            user0[i + 1] = temp;
            
          }
        }
      }

      console.log(user0);
      return user0;
    }
  },

 }

</script>

<style>

</style>
