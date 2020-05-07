<template>
  <div>
    <nav class="navbar is-primary is-fixed-top">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item dog"/>
        <a href="#plansSection"
           class="navbar-item">
          <span>Pricing</span>
          &nbsp;
          <b-icon icon="cart"/>
        </a>
        <a href="#gamesSection"
           class="navbar-item">
          <span>Games</span>
          &nbsp;
          <b-icon icon="gamepad-variant"/>
        </a>
        <div class="navbar-burger burger" @click="showNav = !showNav"
             :class="{ 'is-active': showNav }"
             style="color: white">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <div class="navbar-end navbar-menu" :class="{ 'is-active': showNav }">
        <a href="https://game.shpag.ga/" class="navbar-item">
          <b-icon icon="xbox-controller"/>&nbsp;
          <span>Control panel</span>
        </a>
      </div>
    </nav>
  </div>
</template>

<script>
  import BIcon from "buefy/src/components/icon/Icon";

  export default {
    name: "Navbar",
    components: {BIcon},
    data() {
      return {
        showNav: false,
      }
    }
  }
</script>

<style scoped lang="scss">
  .dog {
    width: 64px;
    height: 4rem;
    background: url('../assets/w_shpaga.svg') no-repeat center;
    background-size: 48px;
    fill: white;
  }

</style>