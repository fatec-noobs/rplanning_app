<template>
  <main class="container">
    <h1>Cliente</h1>
    <form>
      <fieldset>
        <div class="form-group">
          <label>Nome</label>
          <input type="text" class="form-control" placeholder="Digite o seu nome">
        </div>
        <div class="form-group">
          <label>E-mail</label>
          <input type="email" class="form-control" placeholder="Digite o seu email">
        </div>
        <div class="form-group">
          <label>Telefone</label>
          <input type="phone" class="form-control" placeholder="Digite o seu telefone">
        </div>
        <div class="form-group">
          <label>Tipo de cliente</label>
          <select class="form-control">
            <option>Fisica</option>
            <option>Juridica</option>
          </select>
        </div>
        <div class="form-group">
          <label>CPF ou CNPJ</label>
          <input type="text" class="form-control" placeholder="Digite o seu cpf/cnpj">
        </div>
      </fieldset>
      <form-address/>
      <button type="submit" class="btn btn-primary">Salvar</button>
    </form>
  </main>
</template>

<script>
import FormAddress from '~/components/form_pieces/Address.vue'

export default {
  components: {
    FormAddress
  }
}
</script>

