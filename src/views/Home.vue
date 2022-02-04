<template>
  <div id="app">
    <v-btn
      @click="fetchData"
    >
      get data
    </v-btn>
  </div>
</template>


<script>
import Axios from 'axios';

let today = new Date();
let year = today.getFullYear();
let month = today.getMonth() + 1;
month = month >= 10 ? month : '0' + month;
let date = today.getDate() - 1;
date = date >= 10 ? date : '0' + date;
let date_time = year + '-' + month + '-' + date;
date_time = date_time.replace(/\-/g,'');
let url = "https://kobis.or.kr/kobisopenapi/webservice/rest/boxoffice/searchDailyBoxOfficeList.json?key=f5eef3421c602c6cb7ea224104795888&targetDt="+date_time;
console.log(url);

export default {
  el: '#app',
  methods: {
    fetchData: function () {
      Axios.get(url)
        .then(function (response) {
          console.log(response.data);
        })
        .catch(function (error) {
          console.log(error);
        });
    }
  }
}
</script>


