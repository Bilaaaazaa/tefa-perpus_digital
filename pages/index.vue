<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6 box">
                <nuxt-link to="../pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h2>Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
            <div class="col-lg-6 box">
                <nuxt-link to="../buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body">
                            <h2>Cari Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
        <div class="statistik">
            <h1>STATISTIK</h1>
        </div>
        <div class="container-fluid">
        <div class="row my-5 d-flex justify-content-around-5 ">
            <div class="col-lg-6 box">
                <div class="card bg-danger rounded-5">
                <div class="card-body test">
                    <h2 class="text"> 3 pengunjung</h2>
                    </div>
                </div>
            </div>
            <div class="col-lg-6 box">
                
                <div class="card bg-primary rounded-5">
                    <div class="card-body test">
                    <h2 class="text">32 Buku</h2>
                    </div>
                </div>
            </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
    background-image: url('../assets/img/bg-home-kunjungan (1).jpeg');
    color: black;
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
}
.card.bg-buku {
    background: url('../assets/img/bg-home-cari-buku (1).jpg') no-repeat center center;
    background-size: cover;
    color: black;
}
.test{
    display: flex;
    justify-content: center;
    align-items: center; 
}
.box{
    width: 50%;
}
.box a{
    text-decoration: none;
}
</style>