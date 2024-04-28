<template>
  <header>
        <div class="navbar">
          <img src="/src/components/ram_logo.png" alt="logo" style="width: 200px;">
          <div class="links">
            <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
            <router-link class="nav-link" to="/about">About</router-link>
          </div>
        </div>
  </header>
  <div class="cont">
    <div class="info">
      <h1>Guilherme Miranda de Sousa <br> 1979693</h1>
      <h2>Análise e Desenvolvimento de Sistemas <br> UNIMAR <br> 3° Termo A</h2>
    </div>
    <img src="/src/components/ram_sobre.jpg">

  </div>

  <footer>
    <div>
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
</template>

<style>
.cont{
  margin: 200px;
  color: white;
  display: flex;
  align-items: center;
  justify-content: space-around;
  padding: 40px;
}
h2{
  font-weight: 100;
}
.cont img{
  width: 360px;
}
</style>
