<template>
  <tr :id="`entry-row-${row.id}`">
    <td>{{ formatDate(row.date) }}</td>
    <td>{{ row.distance }} km</td>
    <td>{{ row.time }}</td>
    <td>{{ Number(row.speed).toFixed(2) }} km/h</td>
    <td>{{ Number(row.pace).toFixed(2) }} min/km</td>
    <td>
      <RouterLink class="btn btn-primary btn-xs" :to="'/entry/edit/' + row.id">
        <i class="glyphicon glyphicon-pencil" /></RouterLink>
      &nbsp;
      <button class="btn btn-danger btn-xs" @click="$emit('onDelete', row.id)">
        <i class="glyphicon glyphicon-remove" /></button>
    </td>
  </tr>
</template>

<script>
export default {

  props: {
    row: {
      type: Object,
      required: true,
    },
  },

  computed: {},

}
</script>
