<template>
  <main class="container">
    <h1>Clientes</h1>
    <nuxt-link to="/clientes/adicionar">Adicionar novo cliente</nuxt-link>
    <section class="table-responsive-sm">
      <table class="table table-hover">
        <thead>
          <tr>
            <th scope="col">Nome</th>
            <th scope="col">E-mail</th>
            <th scope="col">Phone</th>
            <th scope="col">Tipo</th>
            <th scope="col">CPF</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="client in clientsSortedByDate" :key="client.id">
            <td>{{ client.name }}</td>
            <td>{{ client.email }}</td>
            <td>{{ client.phone }}</td>
            <td>{{ client.type }}</td>
            <td>{{ client.cpf }}</td>
          </tr>
        </tbody>
      </table>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      clients: [],
    }
  },
  async created() {
    const { data } = await this.$axios.get('http://localhost:3333/clients/');
    this.clients = data;
  },
  computed: {
    clientsSortedByDate() {
      return this.clients.sort((a, b) => {
        const dateA = new Date(a.updated_at);
        const dateB = new Date(b.updated_at);
        return dateA < dateB ? 1 : -1;
      });
    }
  }
}
</script>
