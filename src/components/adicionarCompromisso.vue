<template>
  <div class="input-group">
   <!-- <entrada-dados :value="novoCompromisso" @input="associarValor" /> -->
   <entrada-dados @salvar="adicionarCompromisso" v-model="novoCompromisso" />
    <span class="input-group-btn">
      <button @click="adicionarCompromisso" class="btn btn-primary">
        Adicionar
        </button>
    </span>
  </div>
</template>

<script>
import EntradaDados from '@/components/templates/EntradaDados'
export default {
  components: { EntradaDados },
  data() {
    return {
      novoCompromisso: "",
    };
  },
  methods: {
    adicionarCompromisso() {
      this.$emit("adicionarCompromisso", this.novoCompromisso);
      this.novoCompromisso = "";
    },
   // associarValor(valor) {
   //   this.novoCompromisso = valor;
   // },
  }
}
</script>

<style></style>