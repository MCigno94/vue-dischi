<template>
    <main>
        <div class="container">
            <div class="row row-cols-5">
                <div class="cols" v-for="(disc, index) in discs" :key="index">
                    <div class="card">
                        <img :src="disc.poster" class="card-img-top" :alt="disc.title">
                        <div class="card-body">
                            <h5 class="card-title">{{disc.title}}</h5>
                            <p class="card-text"></p>
                        </div>
                    </div>
                    <!-- /.card -->
                </div>
                <!-- /.cols -->
            </div>
            <!-- /.row -->
        </div>
        <!-- /.container -->
    </main>
</template>

<script>
import axios from "axios";

export default {
    name: 'MainComponent',

    data() {
    return {
      API_URL: 'https://flynn.boolean.careers/exercises/api/array/music',
      discs: null,
      loading: false,
      error: null
    }
  },
  methods: {
    callApi(){
        axios
        .get(this.API_URL)
        .then(response => {
            console.log(response);
            this.discs = response.data.response;
            this.loading = response.data.success;

        })
        .catch(error => {
            console.log(error);
            this.error = `Sorry There is a problem! ${error}`
        });
    }   
  },
  mounted(){
      this.callApi()
  },
}
</script>

<style>

</style>