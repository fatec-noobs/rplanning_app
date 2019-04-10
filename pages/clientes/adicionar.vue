<template>
  <main class="container">
    <h1>Cliente</h1>
    <form @submit="addClient">
      <fieldset>
        <div class="form-group">
          <label>Nome</label>
          <input type="text" class="form-control" placeholder="Digite o seu nome" v-model="client.name">
        </div>
        <div class="form-group">
          <label>E-mail</label>
          <input type="email" class="form-control" placeholder="Digite o seu email" v-model="client.email">
        </div>
        <div class="form-group">
          <label>Telefone</label>
          <input type="phone" class="form-control" placeholder="Digite o seu telefone" v-model="client.phone">
        </div>
        <div class="form-group">
          <label>Tipo de cliente</label>
          <select class="form-control" v-model="client.type">
            <option value="fisica">Fisica</option>
            <option value="juridica">Juridica</option>
          </select>
        </div>
        <div class="form-group">
          <label>CPF</label>
          <input type="text" class="form-control" placeholder="Digite o seu cpf" v-model="client.cpf">
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
      client: {
        name: null,
        email: null,
        phone: null,
        type: 'fisica',
        cpf: null,
      },
    }
  },
  methods: {
    async addClient(event) {
      event.preventDefault();
      const content = this.client;
      await this.$axios.post('http://localhost:3333/clients/', { content });
      this.$router.go(-1);
    }
  }
}
</script>

