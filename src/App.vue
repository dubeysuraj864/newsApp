<template>
  <div id="news" v-for="result in results" :key="result">
    <Card :results="result" />
  </div>
</template>

<script>
import axios from 'axios'
import Card from '@/components/Card.vue'
export default {
  name: 'App',
  components: {
    Card,
  },
    data(){
    return {
      results: null,
    }
  },
  methods: {
   async fetchApi(){
      let data = await axios.get('https://newsdata.io/api/1/news?apikey=pub_5012a488556afe12029555864de00d943eb1&q=cryptocurrency');
      this.results= data.data.results;
    console.log("Newz",data.data.results[0].title)

    }
  },

  mounted(){
    this.fetchApi();
  }

}
</script>

<style>
#news{
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  text-align: center;
}
</style>
