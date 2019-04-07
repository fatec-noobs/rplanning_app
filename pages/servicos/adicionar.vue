<template>
  <main class="container">
    <h1>Serviços</h1>
    <p>{{ result }}</p>
    <form @submit="addService">
      <fieldset>
        <div class="form-group">
          <label>Descrição</label>
          <textarea class="form-control" v-model="service.description"></textarea>
        </div>
        <div class="form-group">
          <label>Tipo de unidade</label>
          <select class="form-control" v-model="service.unit_type">
            <option>Metro</option>
            <option>Metro quadrado</option>
            <option>Metro cubico</option>
            <option>Unitario</option>
          </select>
        </div>
        <div class="form-group">
          <label>Preço unitário</label>
          <input type="text" v-model="service.unit_price" class="form-control" placeholder="Digite o preço">
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
        description: 'teste',
        unitType: 'Metro',
        unitPrice: 10,
      },
      result: null
    }
  },
  methods: {
    async addService(event) {
      event.preventDefault();
      const { data } = await this.$axios.get('http://localhost:3333/');
      this.result = data.greeting;
    }
  }
}
</script>
