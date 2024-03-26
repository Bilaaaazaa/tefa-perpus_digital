<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to="../pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h2>Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
            <div class="col-lg-6">
              <nuxt-link to="../buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body">
                            <h2>Cari Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </div>
    <h2 style="margin: 30px"><strong>STATISTIK</strong></h2>
  <div class="Container-fluid">
    <div class="row justify-content-evenly rounded-3">
      <div class="col-5">
        <div class="card1">
          <div class="raccing">
            <h2>3 Pengunjung</h2>
          </div>
        </div>
      </div>
      <div class="col-5">
        <div class="raccing1">
          <h2>33 Buku</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import Chart from 'chart.js/auto';

const labels = [
  'january',
  'febuari',
  'maret',
  'april',
  'mei',
];
const data ={
  labels:labels,
  dataasets:[{
    label: 'pengunjung',
    backgroundColor:'rgb(255, 99, 132)',
    borderColor:'rgb(255, 100, 132)',
    data: [6, 8, 10, 9, 9,],
  }]
};
const  config ={
  type: 'bar',
  data: data,
  options: {}
};
onMounted(()=>{
  const myChart = new Chart(
    document.getElementById('myChart'),
    config
  );
})

</script>

<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
    background-image: url('../assets/img/bg-home-kunjungan.jpeg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
}
.card.bg-buku {
    background: url('../assets/img/bg-home-cari-buku.jpg') no-repeat center center;
    background-size: cover;
}
.raccing {
  height: 200px;
  box-shadow: 1px 1px 10px;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color:   #DCE98A;
}
.raccing1 {
  height: 200px;
  box-shadow: 1px 1px 10px;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color:   #B1EFA1;
}
.card-body h2{
    color: white;
}
</style>