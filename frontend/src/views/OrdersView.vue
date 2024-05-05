<script>
import MainNavigation from '@/components/NavBar.vue';
let id = 0;
export default {
  data() {
    return {
      navHeight: 0,
      counter: 1
    };
  },
  components: {
    Navigation: MainNavigation
  },
  methods: {
    wrap(array) {
      return array.map((element) => {
        return {
          ...element,
          id: id++
        };
      });
    },
    increment() {
      this.counter++;
    },
    decrement(){
      this.counter = Math.max(0,this.counter - 1);
      // this.counter--;  
    }
  },

  mounted() {
    const nav = document.querySelector('.navbar');

    this.navHeight = nav.clientHeight;
  }
};
</script>
<template>
    <navigation />
    <section class="hero" :style="{ '--nav-height': `${navHeight}px` }">
      <div class="product-head">
        <div class="text-head">Pesanan Anda</div>
      </div>
  </section>
  <section class="pesanan p-5">
    <div class="alamat py-4 px-5 border border-black border-3">
      <h2 style="font-weight: 700;">alamat Pengiriman</h2>
      <p>Jln. cupak Gg. V No.1, Sidakarya, Denpasar Selatan, Denpasar, Bali</p>
      <p>80223</p>
    </div>
    <div class="items my-5 border border-black border-3 p-5">
      <h2 class="mb-3">Items</h2>
      <div class="item mt-4 p-4 shadow d-flex align-items-center flex-wrap">
        <img class="border border-3 border-black" src="../assets/img/products/udeng/udeng1.jpeg" alt="">
        <div class="des ms-5">
          <h1>Udeng Putih Sutra Khas Gianyar</h1>
          <p>Jumlah : 2</p>
          <div class="price border border-black border-3 px-3">
            Rp.150.000
          </div>
        </div>
      </div>
      <div class="item mt-4 p-4 shadow d-flex align-items-center flex-wrap">
        <img class="border border-3 border-black" src="../assets/img/products/udeng/udeng2.jpg" alt="">
        <div class="des ms-5">
          <h1>Udeng Merah Kerajaan Sidakarya</h1>
          <p>Jumlah : 1</p>
          <div class="price border border-black border-3 px-3">
            Rp.400.000
          </div>
        </div>
      </div> 
      <div class="details my-5">
        <div class="detail border border-black border-3 p-4">
          <h3>Pesan : <span>Jangan Dibanting dan disayang, karena kalau tidak sayang aku bakal galau 3 generasi</span> </h3>
        </div>
        <div class="detail border border-black border-3 p-4 mt-3">
          <h3>Total Pesanan : 3 Produk</h3>
        </div>
        <div class="detail border border-black border-3 mt-3 p-4">
          <div class="d-flex justify-content-between">
            <h3>Metode Pembayaran</h3>
            <span>COD (Cash Or Duel)</span>
          </div>
        </div>
        <div class="detail border border-black border-3 mt-3 p-4">
          <h3>Rincian Pembayaran</h3>
          <div class="d-flex justify-content-between mt-5">
            <div>
              <h5>Subtotal Produk</h5>
              <h5>Pengiriman</h5>
              <h4>Total Pembayaran</h4>
            </div>
            <div>
              <h5>Rp.550.000</h5>
              <h5>Rp.40.000</h5>
              <h4>Rp.590.000</h4>
            </div>
          </div>
        </div>
        <div class="detail border border-black border-3 mt-3 p-4">
          <h3>Satus :  Dalam Pengiriman</h3>
        </div>
      </div>
    </div>
  </section>
</template>
<style scoped>
.hero {
  padding-top: calc(var(--nav-height) + 10px);
  background-color: #fcf5ed;
}

.product-head {
  background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)),
    url(@/assets/img/products/banner.jpg);
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-position: center;
  background-repeat: no-repeat;
  padding: 5rem 0px;
  transition: all 500ms;
  background-attachment: fixed;
  margin-bottom: 30px;
}

.text-head {
  font-size: 2rem;
  font-family: 'poppins', sans-serif;
  font-weight: 600;
}

.alamat{
  border-radius: 10px;
  font-weight: 700;
  font-size: 1.5rem;
}

.items{
  border-radius: 10px;
}

.item{
  cursor: pointer;
  border-radius: 10px;
}

.item img{
  width: 200px;
  border-radius: 20px;
}

.des{
  font-weight: 500;
  font-size: 1.7rem;
}

.price{
  width: fit-content;
  border-radius: 10px;
}

.detail{
  border-radius: 20px;
}

.detail span{
  font-weight: 400;
  font-size: 1.5rem;
}

.detail h5{
  font-weight: 400;
  font-size: 1.5rem;
}
</style>