<template>
  <div class="panel-body quote">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style>
.panel-body {
  border: 1ppx solid green;
  font-size: 24px;
  color: #6e6e6e;
}
.quote {
  cursor: pointer;
  border: 1px solid black;
  padding: 10px;
  border-radius: 10px;
}
.quote:hover {
  background: #ffe2e2;
}
</style>
