<template>

  <div>

    <div >
      <h1>User rating</h1>
      <Btt v-on:changeSort="chngSrt =! chngSrt"/>
    </div>

    <UserID
      v-on:click="$emit('changeSort')"
      v-for="user in users"
      :key="user.point"
      :user="user"
    />

    <div id="app">
  <h1>Bitcoin Price Index</h1>
  <div v-for="(title, index) in titles" :key="index">
      <div
        class="p-4 shadow-md bg-white rounded border bg-white mb-2 list--item"
      >{{index}}: {{ title.body }}</div>
    </div>

    </div>
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
      userData: [
        { 
          id: 1,
          Ava: "",
          Descr: "",
          UserID: "",
          Name: "",
          Rate: null
        },
      ],
      countryList: []
    }
  },
 mounted() {
    this.getAll();
  },

  watch: {
    searchValue: function() {
      this.getCountries(this.searchValue);
    }
  },

  props: ["searchValue", "region"],

  methods: {
    getAll() {
      axios
        .get("https://restcountries.eu/rest/v2/all")
        .then(response => {
          this.countryList = response.data;
        });
        console.log(this.countryList);
    },

    getCountries() {
      axios
        .get("https://restcountries.eu/rest/v2/name/" + this.searchValue)
        .then(response => {
          this.countryList = [];
          response.data.forEach(e => {
            if (e.region === this.region || this.region === "All") {
              this.countryList.push(e);
            }
          });
          // this.countryList = response.data;
        });
        console.log(this.countryList);
    },
    
  sortData: function() {
    
    var chng = this.chngSrt;
    var user0 = this.userData;
  
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

      
      return user0;
    },
  },

  }

</script>

<style>

</style>
