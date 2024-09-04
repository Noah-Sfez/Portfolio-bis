<template>
  <div id="contributions">
    <CommitWeek
      v-for="(week, i) in data"
      :index="i"
      :key="'week-' + i"
      :week="week"
    />
  </div>
</template>

<script>
import CommitWeek from './CommitWeek.vue';

export default {
  name: 'CommitColumn',
  components: {
    CommitWeek
  },
  props: {
    data: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>
#contributions {
  display: flex;
}
</style>
