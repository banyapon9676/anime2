<template>
  <div
    class="bg-dark"
    bg-danger
    style="
      background-image: url('https://i.pinimg.com/originals/b5/be/43/b5be432ff77705296a32e7c3276c4919.gif');
    "
  >
    <b-navbar toggleable="lg" type="dark" variant="info">
      <img
        overlay
        src="https://f.ptcdn.info/409/013/000/1387207932-PedoZero-o.jpg"
        alt="พี่หมีใส่สูท"
        width="60px"
        height="50px"
      />
      <h1 style="color: white">AnimeLo</h1>
    </b-navbar>
    <b-container fluid>
      <div class="mt-5"></div>
      <b-row>
        <b-col  cols="3" v-for="anime in animelist.top" :key="anime">
          <Anime  :title="anime.title" :image="anime.image_url" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Anime from "@/components/Anime.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    Anime,
  },
  data() {
    return {
      animelist: {},
    };
  },
  mounted() {
    axios({
      method: "GET",
      url: "https://jikan1.p.rapidapi.com/top/anime/1/upcoming",
      headers: {
        "x-rapidapi-key": "d070d378bbmshc8f19ecd0f7796dp11cf3djsn60b74ee1cda7",
        "x-rapidapi-host": "jikan1.p.rapidapi.com",
      },
    }).then((result) => {
      this.animelist = result.data;
    });
  },
};
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: rgb(255, 0, 0);
}
</style>
