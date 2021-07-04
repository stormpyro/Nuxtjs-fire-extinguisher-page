<template>
  <div>
    <b-button id="show-btn" @click="showModal">Rent</b-button>

    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
      <div class="calendar-container">
        <div class="text-container">
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Amet error
            ut consequuntur fugit nemo animi est iusto dolor dignissimos ratione
            quisquam veritatis natus molestiae dolorum aut unde, possimus,
            nesciunt hic repellat voluptatibus omnis! Non fugiat illo voluptates
            incidunt cupiditate tempore!
          </p>
        </div>
        <vc-date-picker
          class="mb-2 align-self-center"
          :value="null"
          color="indigo"
          is-dark
          is-range
        />
        <b-button id="show-btn" variant="outline-danger" @click="addOrder"
          >Order</b-button
        >
      </div>
    </b-modal>
  </div>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  props: ["product"],
  methods: {
    ...mapMutations({ addItem: "addItem" }),
    showModal() {
      this.$refs["my-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
    },
    addOrder: function () {
      this.addItem(this.product.id);
      this.hideModal();
    },
  },
};
</script>
<style scoped>
button {
  width: 100%;
  border: none;
  padding: 0.5rem;
  color: white;
  font-weight: 700;
  padding: 1rem 4rem;
  border-radius: 100rem;
  background-color: rgb(231, 81, 43);
  color: white;
  font-weight: 700;
  transition: 0.5s;
}
.calendar-container {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
p {
  color: grey;
}
.text-container {
  padding: 0.5rem;
}
</style>