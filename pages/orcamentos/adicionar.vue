<template>
  <main class="container">
    <h1>Orçamentos</h1>
    <form @submit="addService">

      <fieldset>
        <div class="form-group">
          <label>Serviços</label>
          <select class="form-control" v-model="service.unit_type" required>
            <option v-for="service in services" value="{{ service.value }}">{{ service.name }}</option>
          </select>
        </div>

        <button class="btn btn-primary">Adicionar mais um</button>
      </fieldset>

      <fieldset>
        <div class="form-group">
          <label>Materiais</label>
          <select class="form-control" v-model="service.unit_type" required>
            <option v-for="material in materials" value="{{ material.value }}">{{ material.name }}</option>
          </select>
        </div>
      </fieldset>

      <fieldset>
        <div class="form-group">
          <label>Clientes</label>
          <select class="form-control" v-model="service.unit_type" required>
            <option v-for="client in clients" value="{{ client.value }}">{{ client.name }}</option>
          </select>
        </div>
      </fieldset>

    </form>
  </main>
</template>

<script>
export default {
  data() {
    return {
      service: [],
      materials: [],
      clients: [],
  },
}
</script>
