<template>

  <div>

    <div v-bind="sortID(users)">
      <h1>User rating</h1>
      <Btt v-on:changeSort="chngSrt =! chngSrt"/>
    </div>

    <div v-bind="sortData(userData)">
      <h1>User rating</h1>
      <Btt v-on:changeSort="chngSrt =! chngSrt"/>
    </div>

    <UserID
      v-on:click="$emit('changeSort')"
      v-for="user in users"
      :key="user.point"
      :user="user"
    />

  </div>

</template>

<script>

import UserID from "./UserID";
import Btt from "./Btt";
import Axios from "axios";

export default {
  name: "Tabs",
  components: {
    UserID, Btt
  },
  data: function() {
    return {
      chngSrt: false,
      options: {
        headings: {
          id: "#",
          name: "Name",
          description: "Descr",
          avatar: "Ava",
          rating: "Rate"
        }
      },
      userData: [],
      users: [
        {
          point: 56,
          id: 1,
          name: "Adrian Schubert",
          about: "Using Vuex4 With Vue3 And Ionic Framework #vuex #ionic #vuejs A simple introduction to using vuex 4 in vuejs version",
          avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
        },
        {
          point: 66,
          id: 2,
          name: "Violet Gates",
          about: "Using Vuex4 With Vue3 And Ionic Framework #vuex #ionic #vuejs A simple introduction to using vuex 4 in vuejs version",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
        },
        {
          point: 46,
          id: 3,
          name: "Steve Jobs",
          about: "Using Vuex4 With Vue3 And Ionic Framework #vuex #ionic #vuejs A simple introduction to using vuex 4 in vuejs version",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
        },
        {
          point: 54,
          id: 4,
          name: "Yassine Smith",
          about: "Using Vuex4 With Vue3 And Ionic Framework #vuex #ionic #vuejs A simple introduction to using vuex 4 in vuejs version",
          avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
        },
        { 
          point: 50,
          id: 5,
          name: "Senior Saez",
          about: "Using Vuex4 With Vue3 And Ionic Framework #vuex #ionic #vuejs A simple introduction to using vuex 4 in vuejs version",
          avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
        }
      ]
    };
  },
  methods: {
  sortID: function() {
    
    var chng = this.chngSrt;
    var user0 = this.users;
  
      for (let j = user0.length - 1; j > 0; j--) {
        for (let i = 0; i < j; i++) {
          if ( (user0[i].point < user0[i + 1].point) === chng ) {
            let temp = user0[i];
            user0[i] = user0[i + 1];
            user0[i + 1] = temp;
            user0[i].id = (i+1);
          }
        }
      }

      console.log(user0);
      return user0;
    }

    
  },
  mounted: function() {
    var mntusr = this;
    Axios.get("https://my-json-server.typicode.com/Vespand/crmm-tasks/users/")
      .then(function(response) {
        
        mntusr.tableData = response.data;
        var tblDt = mntusr.tableData;
        
        console.log(this.userData);
        return this.userData = tblDt;
      })
      .catch(function(error) {
        console.error("Error loading data.");
        console.error(error);
      })
  }
}
</script>

<style>

</style>
