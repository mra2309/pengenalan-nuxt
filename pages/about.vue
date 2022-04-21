<template>
  <div>
    <div class="row my-4">
      <div class="col-md-4 py-2" v-for="(item,index) in response" :key="index">
        <div class="card card-body m-auto text-center">
          <img :src="item.avatar" alt="" class="img-fluid">
          <h6>{{item.email}}</h6>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  layout:"admin",
  auth: false,
  head: {
    title: "Ini About",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        hid: "shosha.co.id",
        name: "shosha.co.id",
        content: "Server pulsa dengan produk terlengkap & pelayanan Non stop 24 jam & transaksi super cepat dengan harga murah dan bersahabat"
      }
    ],
    link: [{ rel: "icon", type: "image/x-icon", href: "/favicon.ico" }],
  },
  beforeMount(){
    this.loadData()
  },
  data(){
    return{
      response : [],
      page:1
    }
  },
  methods:{
    loadData(){
      axios.get(`https://reqres.in/api/users?page=`+this.page)
      .then((res) => {
        this.response = res.data.data
      })
      .catch((error) => {
      })
    }
  },
}
</script>
