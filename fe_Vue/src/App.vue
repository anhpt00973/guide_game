<template>
  <div id="wraper">
    <nav class="navbar is-dark">
      <div class="navbar-brand">
        <router-link to="/" class="navbar-item"
          ><strong>Djackets</strong>
        </router-link>
        <a
          class="navbar-burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbar-menu"
          @click="showMobileMenu = !showMobileMenu"
        >
          <span area-hidden="true"></span>
          <span area-hidden="true"></span>
          <span area-hidden="true"></span>
        </a>
      </div>
      <div
        class="navbar-menu"
        id="navbar-menu"
        v-bind:class="{ 'is-active': showMobileMenu }"
      >
        <div class="navbar-end">
          <router-link to="/summer" class="navbar-item">Summer</router-link>
          <router-link to="/winter" class="navbar-item">Winter</router-link>

          <div class="navbar-item">
            <div class="buttons">
              <router-link to="/log-in" class="button is-light"
                >Log in</router-link
              >
              <router-link to="/cart" class="button in-success">
                <span class="icon"><i class="fas fa-shopping-cart"></i></span>
                <span>Cart</span>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <section class="section">
      <router-view />
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showMobileMenu: false,
    };
  },
};
</script>

<style lang="scss">
@import "../node_modules/bulma";
</style>
