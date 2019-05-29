<template>
  <main class="container">
    <h1>Orçamentos</h1>
    <nuxt-link to="/orcamentos/adicionar">Adicionar novo Orcamento</nuxt-link>
    <section class="table-responsive-sm">
      <table class="table table-hover">
        <thead>
          <tr>
            <th scope="col">ID</th>
            <th scope="col">Cliente</th>
            <th scope="col">Valor</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="budget in budgetsSortedByDate" :key="budget.id">
            <td>{{ budget.id }}</td>
            <td>{{ getClientNameById(budget.client_id) }}</td>
            <td>R$ {{ budget.value }}</td>
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
      budgets: [],
      clients: []
    }
  },
  async created() {
    const budgets = await this.$axios.get('http://localhost:3333/budgets/');
    this.budgets = budgets.data;

    const clients = await this.$axios.get('http://localhost:3333/clients/');
    this.clients = clients.data;
  },
  methods: {
    getClientNameById(id) {
      const client = this.clients.find(client => client.id === id);
      if(client && client.name) {
        return client.name;
      }
    }
  },
  computed: {
    budgetsSortedByDate() {
      return this.budgets;
      return this.budgets.sort((a, b) => {
        const dateA = new Date(a.updated_at);
        const dateB = new Date(b.updated_at);
        return dateA < dateB ? 1 : -1;
      });
    }
  }
}
</script>
