<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view/>
    <footer class="l-footer__wrapper">
        <div class="container">
            <p class="l-footer__copyright-company">CMoney 全曜財經資訊</p>
            <p class="l-footer__copyright-source">資料來源：<span>政府資料開放中心</span></p>
        </div>
    </footer>
  </div>
</template>

<style lang="scss">
    @import "@/assets/scss/main.scss";
</style>
