<template>
  <div>
    <div class="col-6 mb-3">
      <input
        class="form-control"
        type="text"
        name="name"
        v-model="newMember.name"
        placeholder="Nome"
      />
    </div>
    <div class="col-6 mb-3">
      <select
        class="form-select"
        name="instrument"
        v-model="newMember.instrument"
      >
        <option value="" disabled>Selecione o Instrumento</option>
        <option value="Guitarra">Guitarra</option>
        <option value="Baixo">Baixo</option>
        <option value="Bateria">Bateria</option>
        <option value="Teclado">Teclado</option>
        <option value="Vocal">Vocal</option>
      </select>
    </div>
    <div class="col-6">
      <button @click="addMember()" class="btn btn-success">Salvar</button>
      <button
        @click="clearListMembers()"
        class="btn btn-primary"
        style="margin-left: 5px"
      >
        Limpar
      </button>
    </div>

    <Table :listMembers="listMembers"></Table>
  </div>
</template>

<script>
import Table from './Table.vue';

export default {
  components: { Table },
  name: "Form",
  data() {
    return {
      listMembers: [],
      newMember: {
        name: "",
        instrument: "",
      },
    };
  },
  methods: {
    addMember() {
      if (this.newMember.name && this.newMember.instrument) {
        this.listMembers.push(this.newMember);
        this.newMember = {};
      } else {
        alert("Preencha os campos!");
      }
    },
    clearListMembers() {
      this.listMembers = [];
    },
  },
};
</script>

<style scoped>
</style>