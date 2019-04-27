<template>
  <div class="modal modal-club" :class="{ 'is-active': open }">
    <div @click="$emit('set-club-modal-open', !open)" class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title text-centered">{{ currentClub.title }} <b>Club</b></p>
      </header>
      <section class="modal-card-body">

        <div class="content">
          <p class="has-text-centered">
            <img class="club-modal-img" :src="currentClub.imageURL">
          </p>
          <details open>
            <summary><strong>Summary</strong></summary>
            <blockquote>
              {{ currentClub.summary }}
            </blockquote>
          </details>
          <hr>
          <p>
            {{ currentClub.description }}
          </p>
        </div>
      </section>
      <footer class="modal-card-foot">
        <button @click="$emit('set-club-modal-open', !open)" class="button is-primary toggle-club-modal">Close</button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ClubModal',
  props: {
    open: { type: Boolean, required: true },
    currentClub: { type: Object, required: true }
  }
}
</script>

<style scoped>
.modal-club .modal-card .club-modal-img {
  width: 100%;
  max-width: 350px;
  border: 4px solid grey;
}
</style>
