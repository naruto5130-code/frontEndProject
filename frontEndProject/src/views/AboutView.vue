<template>
  <div>
    <button @click="getData">獲取資料</button>
    <div v-if="responseData">
      <p>{{ responseData }}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      responseData: null,
    };
  },
  methods: {
    getData() {
      // 發送 GET 請求
      axios.get('http://localhost:8080/api/hello')
        .then(response => {
          // 處理 API 回應
          this.responseData = response.data;
        })
        .catch(error => {
          // 處理錯誤
          console.error('Error fetching data:', error);
        });
      print(responseData);
    },
  },
};
</script>
