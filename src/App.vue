<template>
  <div id="app">
    <input type="text" v-model="zip" />
    <button @click="askAddress">住所自動入力</button>
    <p>Address:{{ allAddress }}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      zip:"",
      allAddress:"",
    };
  },
  methods: {
    askAddress() {
      axios.get("https://apis.postcode-jp.com/api/v4/postcodes/string?apiKey=string=	U4SDshjc0nvYZTLSI20FCNv6Mk7yB3uRXHXNCT7").then((response) => {this.allAddress = response.data.results[0];})
    },
  }
}
</script>