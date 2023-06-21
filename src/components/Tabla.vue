<template>
  <div class="tabla">
    <b-table
      class="table-dark align-middle text-center"
      hover
      :items="dataTabla"
    >
      <template #cell(calificacion)="data">
        <div v-for="opcion in data.value" :key="opcion">
          <b>{{ opcion }}</b>
        </div>
      </template>
      <template #cell(rating)="rating">
        <b-form-rating
          :value="rating.value"
          variant="warning"
          readonly
          class="rating"
        ></b-form-rating>
      </template>
    </b-table>
  </div>
</template>

<script>
export default {
  props: {
    dataTabla: Array,
  },
};
</script>

<style  scoped>
.tabla {
  width: 100%;
  display: flex;
  justify-content: center;
  padding: 20px;
}

table {
  width: 70%;
}

.rating {
  background: rgb(214, 64, 64);
}
</style>