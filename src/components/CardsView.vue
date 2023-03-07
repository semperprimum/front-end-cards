<template>
  <div>
    <div v-if="cards.length > 0">
      <div class="mt-3" v-for="card in cards" :key="card.id">
        <card-view :card="card" @delete="deleteCard(card.id)" />
      </div>
    </div>
    <div v-else>
      <h1 class="mt-3" style="color: rgba(255, 76, 48)">Список пуст</h1>
    </div>
  </div>
</template>

<script>
import CardView from "./CardView.vue";
export default {
  components: { CardView },
  props: {
    cards: {
      type: Array,
      required: true,
    },
  },
  methods: {
    deleteCard(id) {
      this.$emit("delete-card", id);
    },
  },
};
</script>

<style></style>
