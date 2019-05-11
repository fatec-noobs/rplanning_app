<template>
  <main class="container">
    <h1>Orçamentos</h1>
    <form @submit="saveBudget">

      <fieldset>
        <legend>Materiais</legend>
        
        <div class="form-group" v-for="budget_material, index in budgets_materials" >
          <label>Material {{ index + 1 }}</label>
          <select class="form-control" v-model="budget_material.value" required>
            <option v-for="material in materials_type" :value="material.id">{{ material.description }}</option>
          </select>
          <input v-model="budget_material.amount" class="form-control" type="number" placeholder="quantidade"/>
        </div>

        <button class="btn btn-secondary" @click="removeMaterial">Remover um</button>
        <button class="btn btn-primary" @click="addMaterial">Adicionar mais um</button>
      </fieldset>

      <fieldset>
        <legend>Serviços</legend>
        
        <div class="form-group" v-for="budget_service, index in budgets_services">
          <label>Serviço {{ index + 1 }}</label>
          <select class="form-control" v-model="budget_service.value" required>
            <option v-for="service in services_type" :value="service.id">{{ service.description }}</option>
          </select>
          <input v-model="budget_service.amount" class="form-control" type="number" placeholder="quantidade"/>
        </div>

        <button class="btn btn-secondary" @click="removeService">Remover um</button>
        <button class="btn btn-primary" @click="addService">Adicionar mais um</button>
      </fieldset>

      <fieldset>
        <div class="form-group">
          <label>Cliente</label>
          <select class="form-control" v-model="budget_client.id" required>
            <option v-for="client in client_list" :value="client.id">{{ client.name }}</option>
          </select>
        </div>
      </fieldset>

      <button class="btn btn-primary">Salvar</button>
    </form>
  </main>
</template>

<script>
export default {
  data() {
    return {
      budgets_services: [ { service_id: null, amount: 1 } ],
      budgets_materials: [ { material_id: null, amount: 1 } ],

      services_type: [],
      materials_type: [],

      client_list: [],
      budget_client: { id: null }
    }
  },
  async created() {
    const serices_type = await this.$axios.get('http://localhost:3333/services/');
    this.serices_type = serices_type.data;

    const materials_type = await this.$axios.get('http://localhost:3333/materials/');
    this.materials_type = materials_type.data;

    const client_list = await this.$axios.get('http://localhost:3333/clients/');
    this.client_list = client_list.data;
  },
  methods: {
    addMaterial() {
      this.budgets_materials.push({ material_id: null, amount: 1 })
    },
    removeMaterial() {
      this.budgets_materials.pop(-1)
    },
    addService() {
      this.budgets_services.push({ service_id: null, amount: 1 })
    },
    removeService() {
      this.budgets_services.pop(-1)
    },
    calcValue() {

    },
    async saveBudget(event) {
      event.preventDefault();
      const content = {
        client_id: budget_client.id,

      }
      await this.$axios.post('http://localhost:3333/materials/', { content });
      this.$router.go(-1)
    }
  }
}
</script>
