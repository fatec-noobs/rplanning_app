<template>
  <main class="container">
    <h1>Materiais</h1>
    <nuxt-link to="/materiais/adicionar">Adicionar novo material</nuxt-link>
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
          <tr v-for="material in materialsSortedByDate" :key="material.id">
            <td>{{ material.description }}</td>
            <td>{{ material.unit_type }}</td>
            <td>{{ material.unit_price }}</td>
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
      materials: [],
    }
  },
  async created() {
    const { data } = await this.$axios.get('http://localhost:3333/materials/');
    this.materials = data;
  },
  computed: {
    materialsSortedByDate() {
      return this.materials.sort((a, b) => {
        const dateA = new Date(a.updated_at);
        const dateB = new Date(b.updated_at);
        return dateA < dateB ? 1 : -1;
      });
    }
  }
}
</script>
