<template>
  <div v-if="user">
    <h4> <span class="key"> Name:</span> {{ user.name }}</h4>
    <p> <span class="key"> UserName:</span> {{ user.username }}</p>
    <p> <span class="key"> Email:</span> {{ user.email }}</p>
    <p>Address:</p>
    <ul>
      <li> <span class="key"> Street:</span> {{ user.address.street }}</li>
      <li> <span class="key"> Suite:</span> {{ user.address.suite }}</li>
      <li> <span class="key"> City:</span> {{ user.address.city }}</li>
      <li> <span class="key"> Zip Code:</span> {{ user.address.zipcode }}</li>
      <li>
        GeoLocation: {{ user.address.geo.lat }},{{ user.address.geo.lng }}
      </li>
    </ul>
    <p> <span class="key"> Company:</span> {{ user.company.name }}</p>
    <p> <span class="key">Catch Phrase:</span> "{{ user.company.catchPhrase }}"</p>
    <p> <span class="key">Phone:</span> {{ user.phone }}</p>
    <p> <span class="key"> Website:</span> {{ user.website }}</p>
    <p> <span class="key"> bs:</span> {{ user.company.bs }}</p>
    <button class="button infoButton btn is-pulled-right" @click="goToHome">
      Back to All Users
    </button>
  </div>
</template>
<script>
import { mapGetters } from "vuex";
export default {
  name: "UserFull",
  components: {},
  computed: {
    ...mapGetters(["user"]),
  },
  methods: {
    goToHome() {
      this.$router.push("/");
    },
  },
  created() {
    this.$store.dispatch("getUser", { id: this.$route.params.id });
  },
};
</script>
<style scoped>
ul {
  margin-left: 20px;
}
</style>
