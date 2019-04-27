<template>
  <div id="app">
    <Header @open-add-club-modal="clubAddModalOpen = true" />
    <ClubModal :open="clubModalOpen" :currentClub="currentClub" @set-club-modal-open="clubModalOpen = arguments[0]" />
    <ClubAddModal :open="clubAddModalOpen" @set-club-add-modal-open="clubAddModalOpen = arguments[0]" />
    <main>
      <ClubList :clubs="clubs" @open-club-modal="clubModalOpen = true; currentClubIndex = arguments[0]" />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header";
import ClubList from "./components/clubs/ClubList";
import ClubModal from "./components/clubs/ClubModal";
import ClubAddModal from "./components/clubs/Club_Add_Modal";

export default {

  name: "App",
  components: {
    Header,
    ClubList,
    ClubModal,
    ClubAddModal
  },
  data () {
    return {
      clubModalOpen: false,
      clubAddModalOpen: false,
      currentClubIndex: 0,
      clubs: [
        {
          title: 'Girls On The Run',
          summary: 'Girls on the Run is a social-emotional program developed to build confidence and leadership skills in girls from grades 3-5. Girls practice working together to build healthy, happy habits. A typical session includes a snack and chat, life lesson activities, followed by physical activities where the girls can apply the life lessons in a safe, and low-risk, setting. After these activities, the girls wrap up their time together by imagining themselves applying these skills and reflecting on how their team worked together. The girls are also encouraged to identify another team member who displayed the characteristics during that day. Culminating our season together, the girls participate in a community 5K where they run as a team and cheer for each other as they run.',
          imageURL: 'https://www.dropbox.com/s/x7mhm5c2qvecfby/gotr%202018.jpg?dl=1'
        },
        {
          title: 'Marcus is Cool',
          summary: 'YOU HEARD ME!',
          imageURL: 'http://en.bcdn.biz/Images/2016/11/15/776342f0-86f5-4522-84c9-a02d6b11c766.jpg'
        }
      ]
    };
  },
  computed: {
    currentClub () {
      return this.clubs[this.currentClubIndex];
    }
  }
};
</script>

<style>

</style>
