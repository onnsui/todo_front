<template>
  <tr>
    <td class="bold">
      {{ task.state }}
    </td>
    <td class="bold ellipsis">
      {{ task.title }}
    </td>
    <td>
      {{ task.content }}
    </td>
    <td>
      {{ task.category }}
    </td>
    <td>
      {{ task.due_date }}
    </td>
  </tr>
</template>

<script>
import tasks from '~/config/tasks'

export default {
  props: {
    taskId: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      tasks
    }
  },
  computed: {
    task() {
      return this.tasks.filter(v => v.id === this.taskId)[0]
    }
  }
}
</script>

<style lang="scss" scoped>
tr.active {
  & > td {
    background-color: rgba(#ffffff, 0.2);
  }
}
td {
  background-color: #ffffff;
  font-size: 0.875rem;
  color: #666666;
  padding: 0 0.75rem;
  position: relative;
  height: 3rem;
  cursor: pointer;
  outline: 1px solid #e7e9ed;
  max-width: 0;
}
.bold {
  font-weight: bold;
}
.ellipsis {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
.job-count {
  background-color: #f6f6f7;
  text-align: center;
}
</style>
