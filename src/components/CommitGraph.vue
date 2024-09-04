<template>
  <div class="commit-graph">
    <CommitColumn :data="COMMIT_DATA" />
  </div>
</template>

<script>
import CommitColumn from './CommitColumn.vue';

const COMMIT_DATA = Array.from({ length: 53 }, () =>
  Array.from({ length: 7 }, () => Math.floor(Math.random() * 4))
);

export default {
  name: 'CommitGraph',
  components: {
    CommitColumn
  },
  data() {
    return {
      COMMIT_DATA
    };
  }
};
</script>

<style scoped>
.commit-graph {
  display: flex;
  flex-direction: column;
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
}
</style>
