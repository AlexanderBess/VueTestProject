<template>
  <div class="table">
    <div class="table__title">{{ title }}</div>
    <div class="table__type">{{ type }}</div>
    <div class="table__body">
      <table class="table__content">
        <tr v-for="(name, key) in tableData"
            :key="key">
          <th
            class="table__row"
            :class="tableData.length === key ? 'table__row_last' : ''">{{ name }}</th>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Table",
  props: {
    title: {
      type: String,
      default: ""
    },
    type: {
      type: String,
      default: "Public"
    },
    tableData: {
      type: Array,
      default: []
    }
  }
}
</script>

<style lang="scss" scoped>
  .table {
    background: #363A42;
    box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49), inset 3px 3px 5px rgba(8, 7, 13, 0.25);
    border-radius: 12px;
    color: $white;
    &__title {
      margin: 0 16px 0 16px;
      padding: 12px 0 12px 0;

      font-weight: 700;
      font-size: 14px;
      line-height: 18px;
    }
    &__type {
      padding: 7px 16px 8px 16px;

      box-shadow: 0px 0px 0px rgba(107, 102, 126, 0.49), inset 3px 0px 2px rgba(8, 7, 13, 0.15);
      background: $black2;
      font-weight: 500;
      font-size: 12px;
      line-height: 15px;
    }
    &__body {
      padding: 0 16px 0 16px;
    }
    &__content {
      width: 100%;
    }
    &__row {
      padding: 13px 0 13px 0;
      border: none;
      border-bottom: 1px solid $black2;

      font-weight: 400;
      font-size: 16px;
      line-height: 24px;
      &_last {
        border: none;
      }
    }
  }
</style>
