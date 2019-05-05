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
      <fieldset>
        <div class="form-group">
          <label>CEP</label>
          <input type="text" class="form-control" placeholder="Digite o seu CEP" v-model="address.cep">
        </div>
        <div class="form-group">
          <label>Logradouro</label>
          <input type="text" class="form-control" placeholder="Digite o seu logradouro" v-model="address.publicPlace">
        </div>
        <div class="form-group">
          <label>Número</label>
          <input type="text" class="form-control" placeholder="Digite o seu número" v-model="address.number">
        </div>
        <div class="form-group">
          <label>Complemento</label>
          <input type="text" class="form-control" placeholder="Digite o seu complemento" v-model="address.complement">
        </div>
        <div class="form-group">
          <label>Bairro</label>
          <input type="text" class="form-control" placeholder="Digite o seu bairro" v-model="address.neighborhood">
        </div>
        <div class="form-group">
          <label>Cidade</label>
          <input type="text" class="form-control" placeholder="Digite a sua cidade" v-model="address.city">
        </div>
        <div class="form-group">
          <label>Estado</label>
          <input type="text" class="form-control" placeholder="Digite o seu estado" v-model="address.state">
        </div>
      </fieldset>
      <button type="submit" class="btn btn-primary">Salvar</button>
    </form>
  </main>
</template>

<script>
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
        type: null,
        cpf: null,
      },
      address: {
        cep: null,
        publicPlace: null,
        number: null,
        complement: null,
        neighborhood: null,
        city: null,
        state: null,
      },
    }
  },
  methods: {
    async addClient(event) {
      event.preventDefault();
      const content = this.client;
      content.address = this.address;
      await this.$axios.post('http://localhost:3333/clients/', { content });
      this.$router.go(-1);
    }
  }
}
</script>

