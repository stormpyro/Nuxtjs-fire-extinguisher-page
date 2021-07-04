<template>
  <div class="container">
    <MyItem v-for="item in rentals" :item="item" :key="item.id" />
  </div>
</template>
<script>
import { mapState } from "vuex";
export default {
  layout: "no-nav",
  computed: {
    ...mapState({ rentals: "myRentals" }),
  },
};
</script>
<style scoped>
</style>