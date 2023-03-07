<template>
  <div class="container">
    <form-view @addCard="addCard" />
    <cards-view :cards="cards" @delete-card="deleteCard" />
  </div>
</template>

<script>
import CardsView from "./components/CardsView.vue";
import FormView from "./components/FormView.vue";

export default {
  components: { FormView, CardsView },
  name: "App",
  data() {
    return {
      cards: [
        {
          id: 1,
          title: "Reprehenderit.",
          text: "Laboris aliqua ut ad nisi cillum fugiat pariatur est exercitation labore laboris.",
          color: "red",
        },
        {
          id: 2,
          title: "Laboris.",
          text: "Ex in esse incididunt aliquip laborum.",
          color: "yellow",
        },
        {
          id: 3,
          title: "Cillum.",
          text: "Laborum anim cillum sunt aliquip amet excepteur aliqua.",
          color: "blue",
        },
      ],
    };
  },
  methods: {
    addCard(card) {
      const colorMap = {
        1: "red",
        2: "yellow",
        3: "blue",
      };
      const newCard = {
        id: Date.now(),
        ...card,
        color: colorMap[card.color],
      };
      this.cards.push(newCard);
    },
    deleteCard(payload) {
      this.cards = this.cards.filter((p) => p.id !== payload);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
