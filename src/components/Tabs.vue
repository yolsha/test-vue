<template>
  <div>
    <div v-bind="sortID(users)"></div>
    <UserID  
      v-for="user in users"
      :key="user.point"
      :user="user"
    />
    
  </div>
</template>

<script>
import UserID from "./UserID";

export default {
  name: "Tabs",
  props: {
    sort: {
      type: Object,
      default: () => ({})
    }
  },
  components: {
    UserID
  },
  data: function() {
    return {
      users: [
        {
          point: 56,
          id: 1,
          name: "Adrian Schubert",
          avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
        },
        {
          point: 66,
          id: 2,
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
        },
        {
          point: 46,
          id: 3,
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
        },
        {
          point: 54,
          id: 4,
          name: "Yassine Smith",
          avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
        },
        { 
          point: 50,
          id: 5,
          name: "Senior Saez",
          avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
        }
      ]
    };
  },
  methods: {
  sortID: function() {

    var user0 = this.users;

      for (let j = user0.length - 1; j > 0; j--) {
        for (let i = 0; i < j; i++) {
          if (user0[i].point < user0[i + 1].point) {
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
  }
}
</script>

<style>

</style>
