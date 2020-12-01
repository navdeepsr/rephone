<template>
  <div class="uprofile">
    <div class="upanel">
      <h1 class="uname">@{{ user.uname }}</h1>
      <div class="role" v-if="user.isAdmin">Admin</div>
      <div class="role" v-else>User</div>
      <div class="follower"><strong>Followers: </strong>{{ followers }}</div>
      <button @click="followUser">Follow Me!</button>
      <button @click="newDev">Add New Device</button>
    </div>
    <div>
      <devs
        class="uds"
        v-for="ud in user.udevices"
        :key="ud.id"
        :udev="ud"
        @add-new="newDev"
      />
    </div>
  </div>
</template>

<script>
import devs from "./devs.vue";
export default {
  name: "Profiles",
  components: { devs },
  data() {
    return {
      followers: 0,
      user: {
        fName: "Andy",
        lName: "SR",
        uname: "imnd",
        isAdmin: false,
        udevices: [
          { id: 0, vendor: "Apple", model: "Apple's iPhone" },
          { id: 1, vendor: "Samsung", model: "Android Device" },
          { id: 2, vendor: "Microsoft", model: "Windows Tab" },
        ],
      },
    };
  },
  watch: {
    followers(nCount, oCount) {
      if (oCount < nCount) {
        console.log(`${this.user.uname} has a new follower!`);
      }
    },
  },
  computed: {
    fullName() {
      return `${this.user.fName} ${this.user.lName}`;
    },
  },
  methods: {
    followUser() {
      return this.followers++;
    },
    newDev() {
      console.log(`Added New Device #${this.followers}`);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.uprofile {
  display: grid;
  grid-template-columns: 1fr 4fr;
  gap: 50px;
  padding: 80px 5%;
  align-content: flex-end;
}
.upanel {
  background-color: white;
  border: 1px solid;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  padding: 10px;
}
.role {
  background: rgb(122, 76, 117);
  color: white;
  border-radius: 5px;
  margin-right: auto;
  padding: 5px;
  font-weight: bold;
}
</style>
