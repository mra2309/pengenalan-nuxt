<template>
    <div>
      INI INDEX

      <div>
        <img src="/laptop.png" alt="">
      </div>

      <input type="text" class="form-control" v-model="number.nama">
      <input type="text" class="form-control" v-model="number.alamat">
      {{number}}
      <button class="btn btn-primary" @click="loadings()">
        <b-spinner label="Spinning" small v-if="loading"></b-spinner>
        Chekout
      </button>
    </div>
</template>

<script>
export default {
  name: 'IndexPage',
  auth: false,
  layout:"basic",
  head: {
    title: "Ini Index",
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
  data(){
    return{
      loading:false,
      number:{
        nama:'',
        alamat:''
      }
    }
  },
  methods:{
    loadings(){
      this.loading = true;
    },
    keluarinMessage(){
      alert('mantap')
    }
  }
}
</script>
