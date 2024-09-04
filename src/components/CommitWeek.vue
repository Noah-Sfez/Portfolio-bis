<template>
  <div class="commit-week">
    <CommitDay
      v-for="(commitCount, j) in week"
      :commitCount="commitCount"
      :weekIndex="index"
      :dayIndex="j"
      :key="'week-' + index + '-day-' + j"
    />
  </div>
</template>

<script>
import CommitDay from './CommitDay.vue';

export default {
  name: 'CommitWeek',
  components: {
    CommitDay
  },
  props: {
    week: {
      type: Array,
      required: true
    },
    index: {
      type: Number,
      required: true
    }
  }
};
</script>

<style scoped>
.commit-week {
  display: flex;
  flex-direction: column;
}
</style>
