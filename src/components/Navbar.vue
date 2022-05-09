<script>
export default {
  name: "NavBar",
};
</script>

<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container">
      <a class="navbar-brand" style="color: #f2f2f2" href="/">Al-quran Web</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="/">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/about">Surah</a>
          </li>

        </ul>
      </div>
    </div>
  </nav>

</template>

<style scoped>
.navbar{
  background-color: #008000;
}
.nav-link{
  color: #ffffff;
}
.nav-link:hover{
  color: #181818;
  border-bottom: 3px solid #181818;
}



</style>
