<script setup lang="ts">
import { useAttrs } from 'vue';

const attrs = useAttrs();
</script>

<template>
  <ElTable class="o-table" v-bind="attrs">
    <slot></slot>
  </ElTable>
</template>

<style lang="scss">
.o-table {
  &.el-table {
    --el-table-header-bg-color: var(--o-color-bg4);
    --el-table-row-hover-bg-color: var(--o-color-bg3);
    --el-table-border-color: var(--o-color-division1);
    --el-table-fixed-right-column: none;
    box-shadow: var(--o-shadow-l1);
    color: var(--o-color-text4);
    --el-table-border: none;
    .el-table__empty-block {
      background-color: var(--o-color-bg2);
    }
    thead {
      color: var(--o-color-text1);
    }
    th.el-table__cell.is-leaf {
      border-bottom: none;
    }
    tr {
      background: var(--o-color-bg2);
      position: relative;
      &::after {
        width: calc(100% - 32px);
        background: var(--o-color-division1);
        content: ' ';
        display: inline-block;
        height: 1px;
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);

        z-index: 1;
      }
      &:last-child::after {
        height: 0;
      }
      td {
        color: var(--o-color-text4);
      }
    }

    .el-table__header-wrapper {
      background-color: var(--o-color-greyblue1);
    }
    .el-table__cell {
      padding: var(--o-spacing-h5) 0;
    }
    .cell {
      padding: 0 var(--o-spacing-h5);
    }
    .el-table__inner-wrapper::before {
      background: var(--o-color-bg1);
    }
  }
}
</style>
