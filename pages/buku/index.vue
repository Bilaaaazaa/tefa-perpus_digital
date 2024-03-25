<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">BUKU</h2>
                <div class="my-2">
                    <input type="search" class="form-control rounded-5" placeholder="Mau baca apa hari ini?">
                </div>
                <div class="my-3 text-muted">menampilkan 3 dari 3</div>
                <div class="row">
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card body">
                                <img src="~/assets/img/b1.jpg" class="cover" alt="cover 1">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/b2.jpg" class="cover" alt="cover 2">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/b3.jpg" class="cover" alt="cover 3">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <nuxt-link to="/">
            <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">kembali</button>
        </nuxt-link>
    </div>
</template>
<script setup>
const supabase = useSupabaseClient()

const books = ref([])

const keyword = ref('')

const getbooks = async () => {
    .ilike('judul','%${keyword.value}%')
    if (data) books.value = data
}
</script>

<style scoped>
.card-body {
    width: 100%;
    height: 20em;
    padding: 0;
}
.cover {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
}
.my-02{
    width: 10%;
}
</style>