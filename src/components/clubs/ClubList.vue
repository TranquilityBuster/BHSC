<template>
  <section class="section">
      <div class="container">
        <div class="search-clubs is-flex">
          <input v-model="search" class="input" type="text" placeholder="Search for clubs by name...">
          <strong>{{ filtered.length }} results</strong>
        </div>
        <div v-for="(club, index) in filtered" :key="club.title" class="box club-info toggle-club-modal" @click="$emit('open-club-modal', index)">
          <article class="media">
            <div class="media-left">
              <img class="club-image" :src="club.imageURL">
            </div>

            <div class="media-content">
              <h3 class="title text-centered">{{ club.title }}</h3>
              <div class="content">
                {{ club.summary }}
              </div>
            </div>
          </article>
        </div>

      </div>
    </section>
</template>

<script>
export default {
  name: 'ClubList',
  props: {
    clubs: { type: Array, required: true }
  },
  data () {
    return {
      search: ''
    }
  },
  computed: {
    filtered () {
      if (!this.search) return this.clubs;
      return this.clubs.filter(club => club.title.toLowerCase().includes(this.search.toLowerCase()));
    }
  }
};
</script>

<style scoped>
.search-clubs {
  align-items: center;
  margin-bottom: 20px;
}
.search-clubs input {
  flex: 1;
  width: initial;
}
.search-clubs strong {
  padding-left: 10px;
}
.club-info img.club-image {
  width: 200px;
  border: 4px solid grey;
}
</style>
