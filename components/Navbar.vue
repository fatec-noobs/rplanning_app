<template>
  <nav class="navbar navbar-expand-lg navbar-light">
    <div class="container">
      <nuxt-link class="navbar-brand" to="/">
        <img class="logo" src="~/assets/images/logo.png"/>
      </nuxt-link>
      <button class="navbar-toggler" @click="toggle()" type="button">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="navbar-collapse" v-bind:class="{collapse: isToggled}">
        <ul class="navbar-nav menu">
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/clientes">
              Clientes
              <span class="sr-only">(current)</span>
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/servicos">
              Serviços
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/materiais">
              Materiais
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/orcamentos">
              Orçamentos
            </nuxt-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isToggled: true
    }
  },
  methods: {
    toggle() {
      this.isToggled = !this.isToggled;
    }
  }
}
</script>

<style>
.logo {
  width: 200px;
}

.navbar {
  box-shadow: 0 4px 8px 0 rgba($color-neutral-1-pure, 0.24);
}

.menu {
  margin-left: auto;
}

.nuxt-link-active {
  font-weight: bold;
}
</style>
