<template>
  <fieldset>
    <div class="form-group" v-for="info in infos">
      <label>{{ info.label }}</label>
      <input type="text" class="form-control" :placeholder="info.placeholder">
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

