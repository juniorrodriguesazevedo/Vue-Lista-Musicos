<template>
  <div>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">Nome</th>
          <th scope="col">Instrumento</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="member in listMembers" :key="member.id">
          <td>{{ member.name }}</td>
          <td>{{ member.instrument }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "Table",
  props: {
    listMembers: Array
  },
};
</script>

<style>
.table {
  margin-top: 20px;
  width: 450px;
}
</style>