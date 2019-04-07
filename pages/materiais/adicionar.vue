<template>
  <main class="container">
    <h1>Materiais</h1>
    <form @submit="save">
      <fieldset>
        <div class="form-group">
          <label>Descrição</label>
          <textarea class="form-control" placeholder="Digite a descrição do material" v-model="description">
          </textarea>
        </div>
        <div class="form-group">
          <label>Tipo de unidade</label>
          <select class="form-control" v-model="unit">
            <option>Metro</option>
            <option>Metro quadrado</option>
            <option>Metro cubico</option>
            <option>Unitario</option>
          </select>
        </div>
        <div class="form-group">
          <label>Preço unitário</label>
          <input type="text" class="form-control" v-model="price" placeholder="Digite o preço">
        </div>
      </fieldset>
      <button type="submit" class="btn btn-primary">Salvar</button>
    </form>
  </main>
</template>

<script>
import FormAddress from '~/components/form_pieces/Address.vue'

export default {
  components: {
    FormAddress
  },
  data() {
    return {
      description: undefined,
      unit: 'Metro',
      price: undefined
    }
  },
  methods: {
    save(event) {
      event.preventDefault();
      const { description, unit, price } = this;
      const material = { description, unit, price };
      window.localStorage.setItem(0, JSON.stringfy(material));
    }
  }
}
</script>

