<template>
  <div
    :class="['card', { 'bg-success': state }, { 'bg-danger': !state }]"
  >
    <button @click="clickHandler" type="button" class="close" aria-label="Close">
      <span aria-hidden="true">&times;</span>
    </button>
    <div class="card-body">
      <h5 class="card-title">{{ id }}</h5>
      <p class="card-text">{{ title }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: ['id', 'title'],
  computed: {
    state() {
      return Math.random() >= 0.5;
    }
  },
  methods: {
    clickHandler(){
      this.$emit('removeSensor', this.id);
    }
  }
};
</script>
<style>
.card {
  width: 20rem;
  height: 10rem;
  color: white;
  margin-top: 1rem;
}

.close {
  position: absolute;
  right: 10px;
  top: 5px;
}
</style>
