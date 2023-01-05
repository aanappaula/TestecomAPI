<template>
  <table class="table">
    <thead>
      <tr>
        <th>Cod</th>
        <th>Nome</th>
        <th>Máximo</th>
        <th>Mínimo</th>
        <th>Variação</th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="(quote, key) in quotes" :key="key">
        <td>{{ key }}</td>
        <td>{{ quote.name }}</td>
        <td>{{ quote.high }}</td>
        <td>{{ quote.low }}</td>
        <td>
          <span>
            {{ quote.pctChange }} %
          </span>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: { quotes: { type: Object, required: true } },
};
</script>

<style>
.table{
  padding: 30px;
}
</style>
