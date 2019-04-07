<template>
  <fieldset>
    <div class="form-group" :v-for="info in infos">
      <label>CEP</label>
      <input type="text" class="form-control" placeholder="Digite o seu CEP">
    </div>
    <div class="form-group">
      <label>CEP</label>
      <input type="text" class="form-control" placeholder="Digite o seu CEP">
    </div>
    <div class="form-group">
      <label>Logradouro</label>
      <input type="text" class="form-control" placeholder="Digite o seu logradouro">
    </div>
    <div class="form-group">
      <label>Número</label>
      <input type="text" class="form-control" placeholder="Digite o seu número">
    </div>
    <div class="form-group">
      <label>Complemento</label>
      <input type="text" class="form-control" placeholder="Digite o seu complemento">
    </div>
    <div class="form-group">
      <label>Bairro</label>
      <input type="text" class="form-control" placeholder="Digite o seu bairro">
    </div>
    <div class="form-group">
      <label>Cidade</label>
      <input type="text" class="form-control" placeholder="Digite a sua cidade">
    </div>
    <div class="form-group">
      <label>Estado</label>
      <input type="text" class="form-control" placeholder="Digite o seu estado">
    </div>
  </fieldset>
</template>

<script>
export default {
  data() {
    return {
      infos: [
        {
          'label': 'CEP',
          'placeholder': 'Digite o seu CEP',
        },
        {
          'label': 'Logradouro',
          'placeholder': 'Digite o seu logradouro',
        },
        {
          'label': 'Número',
          'placeholder': 'Digite o seu número',
        },
        {
          'label': 'Complemento',
          'placeholder': 'Digite o seu complemento',
        },
        {
          'label': 'Bairro',
          'placeholder': 'Digite o seu bairro',
        },
        {
          'label': 'Cidade',
          'placeholder': 'Digite o seu cidade',
        },
        {
          'label': 'Estado',
          'placeholder': 'Digite o seu estado',
        },
      ]
    }
  }
}
</script>

