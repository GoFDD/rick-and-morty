<template>
  <div id="app">
    <!-- NAV -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-success">
      <div class="container-fluid">
        <!-- Logo -->
        <img src="../src/assets/logo-min.svg" class="rick" alt="rick and morty">
        <!-- Links da navegação -->
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <RouterLink class="nav-link active" aria-current="page" to="/">Inicio</RouterLink>
            </li>
            <li class="nav-item">
              <RouterLink class="nav-link active" to="/about">Sobre</RouterLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- ver o conteúdo aqui-->
    <router-view></router-view>

    <!-- Rodapé -->
    <footer class="bg-dark text-light">
      <div>Unimar | ADS | {{ new Date().getFullYear()}}</div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style scoped>
footer {
  position: sticky;
  bottom: 0;
  width: 100%;
  background-color: #333;
  color: white;
  padding: 10px 0;
  text-align: center;
  z-index: 1000; 
}


#app {
  margin-bottom: -40px; 
}

</style>
