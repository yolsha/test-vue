<template>
  <div>
    {{usersSort}}
    <UserID
    v-for="user in sortFunc()"
    :key="users.numbe"
    />
  </div>
</template>

<script>
import UserID from "./UserID";

export default {
  name: "Tabs",
  components: {
    UserID
  },
  data: function() {
    return {
      users: [
        {
          point: 56,
          numbe: 5,
          name: "Adrian Schubert",
          avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
        },
        {
          point: 66,
          numbe: 2,
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
        },
        {
          point: 46,
          numbe: 1,
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
        },
        {
          point: 54,
          numbe: 4,
          name: "Yassine Smith",
          avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
        },
        { 
          point: 50,
          numbe: 3,
          name: "Senior Saez",
          avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
        }
      ]
    };
  },
  computed: {
  sortFunc: function () {
      return this.users.sort(
        function(a, b){
          return (a.point > b.point) ? 1 : -1;
        }
    },
  }
}
</script>

<style>

</style>
