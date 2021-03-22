<template>
  <div>
    <UserID
      v-for="user in sortedArray(users)"
      :key="user.point"
      :user="user"
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
          numbe: '',
          name: "Adrian Schubert",
          avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
        },
        {
          point: 66,
          numbe: '',
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
        },
        {
          point: 46,
          numbe: '',
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
        },
        {
          point: 54,
          numbe: '',
          name: "Yassine Smith",
          avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
        },
        { 
          point: 50,
          numbe: '',
          name: "Senior Saez",
          avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
        }
      ],
    };
  },
  computed: {
  sortedArray: function() {
    var user0 = this.users;
    console.log(user0);

    function compare(a, b) {
      if (a.point > b.point){
        return -1;
      }
      if (a.point > b.point)
        return 1;
        return 0;
      }
    return user0.sort(compare);
    }
  }
}
</script>

<style>

</style>
