<template>
  <div id="app">

    <SiteHeader />
    
    <main>

    </main>

  </div>
</template>

<script>
import axios from "axios";
import SiteHeader from './components/HeaderComponent.vue'

export default {
  name: 'App',
  components: {
    SiteHeader,
  },
  data() {
    return {
      API_URL: 'https://flynn.boolean.careers/exercises/api/array/music',
      discs: null,
      loading: true,
      error: null
    }
  },
  methods: {},
  mounted(){
    axios
    .get(this.API_URL)
    .then(response => {
        console.log(response);
        this.discs = response.data;
        this.loading = false;
    })
    .catch(error => {
        console.log(error);
        this.error = `Sorry There is a problem! ${error}`
    });
  },
}
</script>

<style lang="scss">
@use '@/assets/scss/style.scss';

</style>
