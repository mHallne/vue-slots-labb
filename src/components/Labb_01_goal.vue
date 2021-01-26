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

        <template v-slot:tags>
          {{ inspo.tags }}
        </template>

        <template v-slot:description>
          {{ inspo.description }}
        </template>
      </RecomendationCard>
    </div>
  </div>
</template>

<script>
import RecomendationCard from "./RecomendationCard";

export default {
  components: {
    RecomendationCard,
  },
  name: "Labb_01",
  data: () => ({
    loading: false,
    selection: 1,
    inspiration: [
      { header: "Cafe Nero", tags: "Kaffe, Italienskt, prisvärt", description: "Mysigt litet kaffe där man kan ta med sin egen katt"},
      { header: "Vetekatten", tags: "Fika, Klassiskt, Bakverk", description: "Tradiotionellt kaffe där man kan ta med sin egen katt"},
      { header: "Esspresso house", tags: "Kaffe, te, choklad, mat", description: "Kaffekedja där man kan ta med sin egen katt"},
      { header: "Nettans kaffe", tags: "Kaffe, Svenskt kaffe, dyrt", description: "Litet kaffe där man kan ta med sin egen katt"},
      { header: "Preem", tags: "Bensinkaffe, om du har bråttom, bensin", description: "Om du måste ha koffein, men inte bryr dig om smaken på kaffet. Man kan ta med sin egen katt"},
      { header: "Mera kaffe", tags: "Kaffe, choklad, mat, mackor", description: "Mycket kaffe där man kan ta med sin egen katt"},
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
