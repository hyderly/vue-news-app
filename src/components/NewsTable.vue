<template>
  <div>
    
    <table class="table table-striped">
  <thead>
    <tr>
      <th scope="col">Title</th>
      <th scope="col">Source</th>
      <th scope="col">Author</th>
      <th scope="col">Description</th>
      <th scope="col">Image</th>
      <th scope="col">Details</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in items" v-bind:key="item.name">
      <td>{{item.title.substring(0,20) + "..." }}</td>
      <td>{{item.source.name}}</td>
      <td>{{item.author}}</td>
      <td>{{item.description.substring(0,50) + "..." }}</td>
      <td><img :src="item.urlToImage" alt="news-img" width="100px" style="border-radius:5px"></td>
      <td><a class="btn btn-primary">Detail</a></td>
    </tr>

    
    
    
  </tbody>
</table>
  </div>
</template>

<script>

    import Vue from 'vue';
    import axios from 'axios';
    import VueAxios from 'vue-axios';

    Vue.use(VueAxios, axios);


    export default {
    name: 'NewsTable',
    
    data() {
      return {
        items: undefined
      }
    },
    mounted(){
        Vue.axios.get('https://newsapi.org/v2/top-headlines?sources=techcrunch&apiKey=819652370f434ba99524ed65f241897f')
        .then((res) => {
            this.items = res.data.articles;
            console.log(res.data.articles);
        })
    }
    
  }
</script>