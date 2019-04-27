<template>
  <div id="app">
    <Header />
    <ClubModal :open="clubModalOpen" :currentClub="currentClub" @set-club-modal-open="clubModalOpen = arguments[0]" />
    <main>
      <ClubList :clubs="clubs" @open-club-modal="clubModalOpen = true; currentClubIndex = arguments[0]" />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header";
import ClubList from "./components/clubs/ClubList";
import ClubModal from "./components/clubs/ClubModal";

export default {
  name: "App",
  components: {
    Header,
    ClubList,
    ClubModal
  },
  data () {
    return {
      clubModalOpen: false,
      currentClubIndex: 0,
      clubs: [
        {
          title: 'Girls On The Run',
          summary: 'Girls on the Run is a social-emotional program developed to build confidence and leadership skills in girls from grades 3-5. Girls practice working together to build healthy, happy habits. A typical session includes a snack and chat, life lesson activities, followed by physical activities where the girls can apply the life lessons in a safe, and low-risk, setting. After these activities, the girls wrap up their time together by imagining themselves applying these skills and reflecting on how their team worked together. The girls are also encouraged to identify another team member who displayed the characteristics during that day. Culminating our season together, the girls participate in a community 5K where they run as a team and cheer for each other as they run.',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean urna eros, fringilla eget accumsan et, mollis nec mauris. Nullam rutrum risus vel ipsum tempus commodo. Maecenas sollicitudin in metus at consequat. Etiam posuere risus nunc, nec bibendum nisi mollis et. Phasellus eget erat hendrerit justo facilisis bibendum et a metus. Nunc mattis et quam sed dapibus. Nam egestas quam mi, eu placerat elit luctus at. Nam faucibus nisl justo, quis ornare ipsum dapibus eu. Fusce sagittis at augue vel commodo. Ut eget dictum lorem. In eget risus molestie, venenatis enim vel, facilisis leo. Nam eros augue, molestie posuere nulla eu, porttitor egestas augue.\n\nFusce at neque velit. Proin fermentum ante eget nunc consequat pellentesque. Nam aliquam mauris eu porta lobortis. Donec imperdiet ligula a ligula volutpat, vitae viverra justo pharetra. Vivamus ultrices diam ut augue luctus congue. Nam ex dui, scelerisque non varius ut, molestie sed tortor. Aliquam auctor ipsum purus, et tempor metus tincidunt a. Fusce dictum, eros sed commodo faucibus, arcu mauris blandit neque, a aliquam nisl ex non sapien. Nulla congue nunc ut nisi malesuada convallis. Cras maximus dui volutpat tortor cursus porta.\n\nPhasellus nec diam libero. Morbi tortor sapien, tristique et lorem id, vulputate varius nisi. Morbi enim urna, consequat vel nisl ac, rhoncus condimentum tellus. Maecenas iaculis tellus felis, nec elementum mauris blandit eu. Morbi sit amet velit eget ligula lobortis molestie. Nam pharetra massa tristique elit iaculis vestibulum. Etiam id maximus orci. Phasellus suscipit eros at libero fermentum, a pulvinar quam eleifend. In hac habitasse platea dictumst. Mauris quis eleifend purus, et mollis ipsum.',
          imageURL: 'https://www.dropbox.com/s/x7mhm5c2qvecfby/gotr%202018.jpg?dl=1'
        },
        {
          title: 'Marcus is Cool',
          summary: 'YOU HEARD ME!',
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean urna eros, fringilla eget accumsan et, mollis nec mauris. Nullam rutrum risus vel ipsum tempus commodo. Maecenas sollicitudin in metus at consequat. Etiam posuere risus nunc, nec bibendum nisi mollis et. Phasellus eget erat hendrerit justo facilisis bibendum et a metus. Nunc mattis et quam sed dapibus. Nam egestas quam mi, eu placerat elit luctus at. Nam faucibus nisl justo, quis ornare ipsum dapibus eu. Fusce sagittis at augue vel commodo. Ut eget dictum lorem. In eget risus molestie, venenatis enim vel, facilisis leo. Nam eros augue, molestie posuere nulla eu, porttitor egestas augue.\n\nFusce at neque velit. Proin fermentum ante eget nunc consequat pellentesque. Nam aliquam mauris eu porta lobortis. Donec imperdiet ligula a ligula volutpat, vitae viverra justo pharetra. Vivamus ultrices diam ut augue luctus congue. Nam ex dui, scelerisque non varius ut, molestie sed tortor. Aliquam auctor ipsum purus, et tempor metus tincidunt a. Fusce dictum, eros sed commodo faucibus, arcu mauris blandit neque, a aliquam nisl ex non sapien. Nulla congue nunc ut nisi malesuada convallis. Cras maximus dui volutpat tortor cursus porta.\n\nPhasellus nec diam libero. Morbi tortor sapien, tristique et lorem id, vulputate varius nisi. Morbi enim urna, consequat vel nisl ac, rhoncus condimentum tellus. Maecenas iaculis tellus felis, nec elementum mauris blandit eu. Morbi sit amet velit eget ligula lobortis molestie. Nam pharetra massa tristique elit iaculis vestibulum. Etiam id maximus orci. Phasellus suscipit eros at libero fermentum, a pulvinar quam eleifend. In hac habitasse platea dictumst. Mauris quis eleifend purus, et mollis ipsum.',
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
