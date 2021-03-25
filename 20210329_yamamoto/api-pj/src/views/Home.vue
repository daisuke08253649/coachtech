<template>
  <div id="home">
    <input type="text" v-model="postcode" maxlength="7" />
    <button @click="searchAddress">住所自動入力</button>
    <p>Address:{{addressdata}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return{
      addressdata:"",
      apikey:"fe99bc357b10c34acd98782807a0a2cf",
    };
  },
  methods:{
    searchaddress() {
      let url= "https://apis.postcode-jp.com/api/v3/postcodes/"
      this.postcode 
      "apikey=" 
      this.apikey;
      axios.get(url).then((res) => {
        this.addressdata = res.data.alladdress;
      });
    },
  },
};
</script>
