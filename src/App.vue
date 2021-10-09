<template>
  <section>
    <cabecalho :valor= "titulo" />
  <div class="container">
  <adicionar-compromisso @adicionarCompromisso="adicionarCompromisso" />
  <listar-compromissos :compromissos="compromissos"/>
    <footer>
      <em>Altere aqui o título da sua agenda</em>
      <entrada-dados v-model="titulo" type="text" />
    </footer>
  </div>
  <rodape />
  </section>
</template>

<script>
  import cabecalho from "@/components/cabecalho";
  import rodape from "@/components/rodape";
  import listarCompromissos from "@/components/listarCompromissos";
  import adicionarCompromisso from "@/components/adicionarCompromisso";
  import EntradaDados from "@/components/templates/EntradaDados";
export default {
  name: "App",
  components: { cabecalho, rodape, listarCompromissos, adicionarCompromisso, EntradaDados },
  data() {
    return {
      titulo: "Minha agenda de compromissos",
      novoCompromisso: "",
      compromissos: [
        { titulo: "Aniversário do Tio Marco 03/10", checked: true},
        { titulo: "Apresentação de teatro do Davi 23/10", checked: false},
      ],
    };
  },
  methods: {
    adicionarCompromisso(novoCompromisso) {
      this.compromissos.push({
        titulo: novoCompromisso,
        checked: false,
      });
    },
  },
};
</script>

<style>
.container {
  width: 40%;
  margin: 20px auto 0px auto;
  font-family: sans-serif;
}

ul li {
  list-style: none;
}

.removed {
  color: #ff4040;
}

.removed label {
  text-decoration: line-through;
}

</style>
