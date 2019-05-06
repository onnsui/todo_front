<template>
  <div class="list-wrapper">
    <div class="list-header"></div>
    <div class="list-body">
      <task-table></task-table>
    </div>
    <div class="list-footer"></div>
  </div>
</template>

<script>
import TaskTable from '~/components/Task/Table'

export default {
  components: {
    TaskTable
  }
}
</script>

<style>
</style>
