<template>
  <div class="q-pa-md">
    <q-table
      title="Treats"
      :rows="rows"
      :columns="columns"
      row-key="name"
    />
  </div>
</template>
<script setup>

import { ref } from 'vue'

const columns = ref([
  { name: 'id', align: 'left', label: 'id', field: 'id', sortable: true },
  { name: 'fname', align: 'left', label: 'fname', field: 'fname', sortable: true },
  { name: 'lname', align: 'left', label: 'lname', field: 'lname', sortable: true },
  { name: 'username', align: 'left', label: 'username', field: 'username', sortable: true },
  { name: 'avatar', align: 'center', label: 'avatar', field: 'avatar'},

])

const rows = ref([])

const fetchData = () => {
  fetch("https://www.melivecode.com/api/users")
  .then(res => res.json())
  .then((result) => {
    rows.value = result
  })
}
fetchData();


</script>