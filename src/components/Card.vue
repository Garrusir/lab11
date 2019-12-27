<template>
  <div class="col s12 m6 l3">
    <div class="card red darken-1" :class="{ green: state }">
      <div class="card-content white-text">
        <span class="card-title">{{ id }}</span>
        <p>{{ name }}</p>
      </div>
      <div class="card-action col s12">
        <a @click="$emit('removeCard', id)">Удалить</a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    state: Boolean,
    id: Number,
    name: String
  }
};
</script>
<style type="text/css"></style>
