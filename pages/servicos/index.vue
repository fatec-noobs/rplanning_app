<template>
  <main class="container">
    <h1>Serviços</h1>
    <nuxt-link to="/servicos/adicionar">Adicionar novo serviço</nuxt-link>
    <section class="table-responsive-sm">
      <table class="table table-hover">
        <thead>
          <tr>
            <th scope="col">Descrição</th>
            <th scope="col">Tipo</th>
            <th scope="col">Preço</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="service in servicesSortedByDate" :key="service.id">
            <td>{{ service.description }}</td>
            <td>{{ service.unitType }}</td>
            <td>{{ service.unitPrice }}</td>
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
      services: [],
    }
  },
  async created() {
    const { data } = await this.$axios.get('http://localhost:3333/services/');
    this.services = data;
  },
  computed: {
    servicesSortedByDate() {
      return this.services.sort((a, b) => {
        const dateA = new Date(a.updated_at);
        const dateB = new Date(b.updated_at);
        return dateA < dateB ? 1 : -1;
      });
    }
  }
}
</script>
