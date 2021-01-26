<template>
  <div 
    id="app"
    class="d-flex flex-row flex-wrap mb-6"
  >
    <div 
      v-for="(inspo, i) in inspiration" 
      :key="i"
      >
      <RecomendationCard>
        <template v-slot:header>
          {{ inspo.header }}
        </template>

        <template v-slot:content>
          <v-img
            height="250"
            :src=inspo.image
          ></v-img>

          <v-chip
            v-for="(tag, i) in inspo.tags" 
            :key="i"
            class="ma-2"
            color="green"
            text-color="white"
          >
            {{ tag }}
          </v-chip>

          <v-divider></v-divider>

          <div class="font-family: 'Avenir', Helvetica, Arial, sans-serif;"> {{ inspo.description }} </div>
        </template>
      </RecomendationCard>
    </div>
  </div>
</template>

<script>
import RecomendationCard from "./RecomendationCard_02";

export default {
  components: {
    RecomendationCard,
  },
  name: "Labb_01",
  data: () => ({
    loading: false,
    selection: 1,
    inspiration: [
      { header: 'Rinse FM', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis volutpat at leo quis finibus. Phasellus vitae facilisis nisi.', image: 'https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg'},
      { header: 'Night Service Only', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'Curabitur vel porttitor urna, quis sollicitudin felis. Aenean finibus, purus non pellentesque convallis, risus lectus ornare velit, ac sodales dolor sem in eros.', image: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg'},
      { header: 'Quality Goods Records', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'Donec congue, erat non accumsan cursus, diam nisl ultricies lorem, nec consequat velit eros nec tellus. In hac habitasse platea dictumst.', image: 'https://cdn.vuetifyjs.com/images/cards/road.jpg'},
      { header: '4NC¥', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'Maecenas ut porttitor nisi, lacinia tincidunt dui. Suspendisse semper neque id tortor efficitur, in volutpat nisi elementum. Vivamus vitae fermentum ipsum. Curabitur luctus erat tortor, id sollicitudin quam iaculis aliquet. Sed id scelerisque augue. In semper lacinia enim eget malesuada. Nam aliquam nisl eros, vel consectetur felis volutpat in.', image: 'https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg'},
      { header: 'lwizdubstep', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'In maximus nibh leo, at lacinia mauris euismod ac.', image: 'https://cdn.vuetifyjs.com/images/cards/house.jpg'},
      { header: 'Dispatch Recs | Ant TC1', tags: ['Maecenas', 'Lorem', 'Duis'], description: 'Nam sed metus at justo consequat gravida id quis tortor. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Morbi vel pharetra ex.', image: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    ],
  }),
  methods: {
    reserve() {
      this.loading = true;
      setTimeout(() => (this.loading = false), 2000);
    },
    rate() {
      this.loading = true;
      setTimeout(() => (this.loading = false), 2000);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
