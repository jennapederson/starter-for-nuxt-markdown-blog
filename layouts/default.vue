<template>
  <div>
    <nav class="navbar is-spaced" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <nuxt-link to="/" class="navbar-item">
          Starter for Nuxt Markdown Blog
        </nuxt-link>

        <a role="button"
          :class="{'is-active': showHeaderNavbarMenu}"
          class="navbar-burger burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="header-navbar-menu"
          @click="toggleHeaderNavbarMenu">
          <span aria-hidden="true" />
          <span aria-hidden="true" />
          <span aria-hidden="true" />
        </a>
      </div>

      <div id="header-navbar-menu" class="navbar-menu" :class="{'is-active': showHeaderNavbarMenu}">
        <div class="navbar-end">
          <nuxt-link to="/" class="navbar-item" exact-active-class="is-active">
            Home
          </nuxt-link>
        </div>
      </div>
    </nav>
    <section class="section">
      <nuxt />
    </section>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      showHeaderNavbarMenu: false
    }
  },
  methods: {
    toggleHeaderNavbarMenu () {
      this.showHeaderNavbarMenu = !this.showHeaderNavbarMenu
    }
  }
}
</script>

<style>
</style>
