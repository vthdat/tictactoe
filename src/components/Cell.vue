<template>
    <div @click="$emit('click')" class="cell">
      <span v-if="value !== ''">{{ value }}</span>
    </div>
</template>

<script>
  export default {
    props: {
      value: String,
    }
  }
</script>

<style>
  .cell {
    width: 150px;
    height: 150px;
    border: 1px solid rgb(75,75,75);
    font-size: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>