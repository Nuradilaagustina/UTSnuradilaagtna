<script setup>
import NavBar from "../components/Navbar.vue";

</script>

<template>
  <main>
    <NavBar />
    <div class="card bg-dark text-white">
      <img src="../assets/bghijauu.jpg" class="card-img" alt="...">
      <div class="card-img-overlay">
        <h5 class="card-title">Welcome to my web</h5>
        <p class="card-text">Ini adalah website yang berisikan beberapa ayat alquran dengan API dari Quran.com untuk pemenuhan tugas UTS Pemrogaman Web</p>
        <p class="card-text">"Bacalah Al-quran, karna Al-quran akan datang pada hari kiamat nanti sebagai syafi' (pemberi syafa'at) bagi yang membacanya"</p>
        <p class="card-text">(HR.Muslim)</p>
      </div>
    </div>
  </main>
</template>

<style>
.card-img-overlay{
  margin-top: 125px;
  text-align: center;
  font-weight: bold;
  }
.card-title{
  font-size: 55px;
}
.card-text{
  margin-top: 20px;
  font-size: 18px;
}
</style>
