<template>
  <main class="container">
    <h1>Serviços</h1>
    <form @submit="addService">
      <fieldset>
        <div class="form-group">
          <label>Descrição</label>
          <textarea class="form-control" v-model="service.description" placeholder="Digite a descrição" required>
          </textarea>
        </div>
        <div class="form-group">
          <label>Tipo de unidade</label>
          <select class="form-control" v-model="service.unitType" required>
            <option value="metro">Metro</option>
            <option value="metro quadrado">Metro quadrado</option>
            <option value="metro cubico">Metro cubico</option>
            <option value="unitario">Unitario</option>
          </select>
        </div>
        <div class="form-group">
          <label>Preço unitário</label>
          <input type="number" v-model="service.unitPrice" class="form-control" placeholder="Digite o preço" required>
        </div>
      </fieldset>
      <button type="submit" class="btn btn-primary">Salvar</button>
    </form>
  </main>
</template>

<script>
export default {
  data() {
    return {
      service: {
        description: null,
        unitType: 'metro',
        unitPrice: null,
      },
      result: null
    }
  },
  methods: {
    async addService(event) {
      event.preventDefault();
      const content = this.service;
      await this.$axios.post('http://localhost:3333/services/', { content });
    }
  }
}
</script>
