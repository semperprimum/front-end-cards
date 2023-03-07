<template>
  <div>
    <div class="card" :class="card.color">
      <div class="card-body">
        <div class="d-flex justify-content-between">
          <h5 class="card-title text-start">{{ card.title }}</h5>
          <button class="delete-btn" @click="$emit('delete', card.id)">
            <i class="fa-solid fa-circle-xmark"></i>
          </button>
        </div>
        <p class="card-text text-start">
          {{ card.text }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.red {
  background-color: rgba(255, 0, 0, 0.4);
}

.yellow {
  background-color: rgba(255, 255, 159, 1);
}

.blue {
  background-color: rgba(137, 196, 244, 1);
}

.delete-btn {
  background: none;
  border: none;
  color: rgba(210, 77, 87, 1);
}
</style>
