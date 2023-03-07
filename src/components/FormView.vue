<template>
  <div>
    <div class="form-floating mb-3">
      <input
        v-model="card.title"
        type="text"
        class="form-control"
        id="floatingInput"
        placeholder="name@example.com"
      />
      <label for="floatingInput">Card Heading</label>
    </div>
    <div class="form-floating">
      <textarea
        v-model="card.text"
        class="form-control"
        placeholder="Leave a comment here"
        id="floatingTextarea2"
        style="height: 100px"
      ></textarea>
      <label for="floatingTextarea2">Card Text</label>
    </div>
    <div class="form-floating mt-3">
      <select
        v-model="card.color"
        class="form-select"
        id="floatingSelect"
        aria-label="Floating label select example"
      >
        <option selected disabled>Color</option>
        <option value="1">Red</option>
        <option value="2">Yellow</option>
        <option value="3">Blue</option>
      </select>
      <label for="floatingSelect">Pick a color</label>
    </div>
    <button
      @click="addCard"
      type="submit"
      class="btn btn-success form-control mt-3"
    >
      Submit
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      card: {
        title: "",
        text: "",
        color: "",
      },
    };
  },
  methods: {
    addCard() {
      this.id = Date.now();
      this.$emit("addCard", this.card);
      this.title = "";
      this.text = "";
      this.color = null;
    },
  },
};
</script>

<style></style>
