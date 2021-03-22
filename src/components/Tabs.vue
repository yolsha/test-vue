<template>
  <div>
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
    msg: String
  },
  components: {
    UserID
  },
  data: function() {
    return {
      users: [
        {
          point: 56,
          numbe: uRate(),
          name: "Adrian Schubert",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
        },
        {
          point: 66,
          numbe: uRate(),
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
        },
        {
          point: 46,
          numbe: uRate(),
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
        },
        {
          point: 54,
          numbe: uRate(),
          name: "Yassine Smith",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
        },
        { 
          point: 50,
          numbe: uRate(),
          name: "Senior Saez",
          avatar:
            "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
        }
      ],
      userrate: []
    };
  },
  methods: {
    uRate() {
      
    }
  }
};
</script>

<style>

</style>
