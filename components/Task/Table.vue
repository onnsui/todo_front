<template>
  <div class="talent-table">
    <table>
      <colgroup>
        <col style="width: 386px;">
        <col style="width: 122px;">
        <col style="width: 335px;">
        <col style="width: 159px;">
        <col style="width: 74px;">
      </colgroup>
      <thead>
        <tr>
          <th>
            状態
          </th>
          <th>
            タスク名
          </th>
          <th>
            内容
          </th>
          <th>
            カテゴリ
          </th>
          <th>
            期限
          </th>
        </tr>
      </thead>
      <tbody>
        <task-table-row
          v-for="(task, key) in tasks"
          :task-id="task.id"
          :key="key"
        />
      </tbody>
    </table>
  </div>
</template>

<script>
import TaskTableRow from '~/components/Task/TableRow'
import tasks from '~/config/tasks'

export default {
  components: {
    TaskTableRow
  },
  data() {
    return {
      tasks
    }
  }
}
</script>

<style lang="scss" scoped>
.talent-table {
  table {
    border-collapse: collapse;
    th {
      background-color: #f6f6f7;
      color: #666666;
      font-size: 0.75rem;
      font-weight: bold;
      height: 2rem;
      text-align: left;
      padding: 0 0.75rem;
      position: relative;
      outline: 1px solid #e7e9ed;
    }
    .favorite {
      padding: 0;
    }
  }
}
.el-dropdown-menu {
  padding: 0;
  max-height: 10rem;
  overflow: scroll;
  &__item {
    padding: 0 0.5rem;
  }
  /deep/ .popper__arrow {
    display: none;
  }
  .star-item {
    height: 2.25rem;
    position: relative;
    width: 100%;
    .s-icon {
      margin: auto;
      padding-top: 0.125rem;
    }
  }
}
.data-empty {
  line-height: 6rem;
  background-color: #ffffff;
  text-align: center;
}
.el-dropdown,
.el-dropdown-link {
  width: 100%;
  height: 100%;
  cursor: pointer;
  .s-icon {
    margin: auto;
  }
}
.el-dropdown-link {
  padding-top: 8px;
}
</style>
