<template>
  <header>
    <div class="container-fluid h-100">
      <div class="row row-cols-2 justify-content-between align-items-center h-100">
        <div class="logo cols">
          <img src="@/assets/img/Spotify.png" alt="">
        </div>
        <!-- /.logo -->
        <div class="cols h-100">
              <div class="row row-cols-2 align-items-center text-end h-100 p-1 pe-3">
    <div class="artist cols h-100">
        <select class="artist_form text-white h-100 rounded-3" id="floatingSelectGrid" aria-label="Floating label select example">
            <option selected>Seleziona l'artista</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>
    </div>
    <!-- /.artist -->
    <SelectBox v-model="selectOption" @seleziona="select"/>
    </div>
    <!-- /.row -->
        </div>
        <!-- /.cols -->
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container-fluid -->
  </header>
</template>

<script>
import SelectBox from '@/components/SelectBoxGenre.vue';
import state from '@/state.js';

export default {
  name: 'HeaderComponent',
    components: {
    SelectBox
  },
    data(){
    return {
      selectOption: ''
    }
  },
  methods: {
    select() {
      console.log('Searching...');
      console.log(this.selectOption);
      state.selectOption = this.selectOption;
      console.log(state);
    }
  }
}
</script>

<style lang="scss" scoped>
  select {
    background-color: #1E2D3B;
    padding: 0.25rem 0;
  }
</style>