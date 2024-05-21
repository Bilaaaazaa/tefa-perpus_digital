<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6 box ">
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h2>Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
            <div class="col-lg-6 box">
              <nuxt-link to="/buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body">
                            <h2>Cari Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </div>
    <div class="statistik">
      <h1>STATISTIK</h1>
    </div>
      <div class="row my-5 d-flex justify-content-evenly ">
        <div class="col-lg-6 box">
          <NuxtLink to="/pengunjung">
            <div class="card raccing rounded-5">
              <div class="card-body text">
                <h3 class="pt-4"><span class="no">{{jmlh_pengunjung}}</span>Pengunjung</h3>
              </div>
            </div>
          </NuxtLink>
          </div>
        <div class="col-lg-6 box">
          <NuxtLink to="/buku">
            <div class="card raccing1 rounded-5">
              <div class="card-body text">
                <h3 class="pt-4"><span class="no">{{jmlh_buku}}</span>Buku</h3>
              </div>
            </div>
          </NuxtLink>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <Statistik />
        </div>
      </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const jmlh_pengunjung = ref(0)
const jmlh_buku = ref(0)

async function getjmlh_pengunjung(){
  const{error, data, count} = await supabase
  .from("pengunjung")
  .select('*', {count: 'exact'})
  if (count) jmlh_pengunjung.value = count
}

async function getjmlh_buku(){
  const{error, data, count} = await supabase
  .from("Buku")
  .select('*', {count: 'exact'})
  if (count) jmlh_buku.value = count
}

onMounted(() => {
  getjmlh_pengunjung()
  getjmlh_buku()
})

useHead({ title: "Home / PERPUSTAKAAN DIGITAL" })
</script>

<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
    background-image: url('~/assets/img/kunjungan.jpeg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
}
.card.bg-buku {
    background: url('~/assets/img/bg-home-cari-buku (1).jpg') no-repeat center center;
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
    color: black;
} 
.box {
  width: 50%;
}
.box a{
  text-decoration: none;
}
</style>
