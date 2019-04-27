<template>
  <div class="modal modal-add-club" :class="{ 'is-active': open }">
    <div @click="$emit('set-club-add-modal-open', !open)" class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title text-centered">Add New Club</p>
      </header>
      <section class="modal-card-body">
very cool
      </section>
      <footer class="modal-card-foot">
        <button @click="$emit('set-club-add-modal-open', !open)" class="button is-primary toggle-club-add-modal">Close</button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ClubAddModal',
  props: {
    open: { type: Boolean, required: true }
  }
};
</script>

<style scoped>
</style>
