<template>
  <div>
    <section>
      <ul class="list">
        <li class="items" v-for="(el, index) in taskList" :key="index">
          {{ el.task }}
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    taskList: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style></style>
