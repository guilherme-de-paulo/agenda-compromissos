<template>
  <ul>
    <li v-for="(compromisso, index) in compromissos"
    :key="index"
    :class="{ removed: compromisso.checked }"
    >
      <input type="checkbox" 
      v-model="compromisso.checked">
      <label>{{compromisso.titulo}} </label>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    compromissos: {
        type: Array,
        default() {
            return [{ titulo: "Atividade padrão", checked: false }];
           },
        },
    },
};
</script>

<style>

</style>