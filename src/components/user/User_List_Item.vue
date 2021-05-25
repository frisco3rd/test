<template>
  <div class="card cardHolder">
    <div class="card-content">
      <div class="content">
        <h3 class="card-head white">{{ user.name }}</h3>
        <div class="card-text pb-2">
        <p> <span class="key">UserName:</span> {{ user.username }}</p>
        <p> <span class="key">Company:</span> {{ user.company.name }}</p>
        <p> <span class="key">Zip Code:</span> {{ user.address.zipcode }}</p>
        </div>
        <router-link
          :to="`/users/${user.id}`"
          class="button infoButton btn"
        >
          <strong>More Details</strong>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "UserListItem",
  props: ["user"],
};
</script>
<style scoped>
.card {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  margin: 0;
  padding: 0;
  width: 250px;
}
</style>
