<template>
  <div>
    <label class="notes">
      <span class="name">备注</span>
      <input type="text" placeholder="在这里输入备注">
    </label>
  </div>
</template>

<script lang="ts">
export default {
name: "Notes"
}
</script>

<style lang="scss" scoped>
.notes{
  font-size: 14px;
  display: flex;
  align-items: center;
  background: #E9FDE4;
  padding-left: 16px ;

  .name{
    padding-right: 16px;
  }
  input{
    height: 62px;
    flex-grow: 1;
    background: transparent;
    border: none;
    padding-right: 16px;
  }
}
</style>