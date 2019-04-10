<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <nuxt-link class="navbar-brand" to="/">
      R&Planning
    </nuxt-link>
    <button class="navbar-toggler" @click="toggle()" type="button">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="navbar-collapse" v-bind:class="{collapse: isToggled}">
      <ul class="navbar-nav">
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
      </ul>
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
