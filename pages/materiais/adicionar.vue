<template>
  <main class="container">
    <h1>Materiais</h1>
    <form @submit="addMaterial">
      <fieldset>
        <div class="form-group">
          <label>Descrição</label>
          <textarea class="form-control" placeholder="Digite a descrição do material" v-model="material.description">
          </textarea>
        </div>
        <div class="form-group">
          <label>Tipo de unidade</label>
          <select class="form-control" v-model="material.unitType">
            <option value="metro">Metro</option>
            <option value="metro quadrado">Metro quadrado</option>
            <option value="metro cubico">Metro cubico</option>
            <option value="unitario">Unitario</option>
          </select>
        </div>
        <div class="form-group">
          <label>Preço unitário</label>
          <input type="text" class="form-control" v-model="material.unitPrice" placeholder="Digite o preço">
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
      material: {
        description: null,
        unitType: 'metro',
        unitPrice: null,
      },
    }
  },
  methods: {
    async addMaterial(event) {
      event.preventDefault();
      const content = this.material;
      await this.$axios.post('http://localhost:3333/materials/', { content });
      this.$router.go(-1)
    }
  }
}
</script>

