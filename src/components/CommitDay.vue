<template>
  <div class="commit-day" :class="['commit-count-' + commitCount, { 'commit-day-blink': isBlinking }]">
  </div>
</template>

<script>
export default {
  name: 'CommitDay',
  props: {
    commitCount: {
      type: Number,
      required: true
    },
    weekIndex: {
      type: Number,
      required: true
    },
    dayIndex: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      isBlinking: false
    };
  },
  mounted() {
    this.startBlinking();
  },
  methods: {
    startBlinking() {
      setInterval(() => {
        this.isBlinking = !this.isBlinking;
      }, Math.random() * 2000 + 1000); // Change blink interval randomly between 1 and 3 seconds
    }
  }
};
</script>

<style scoped>
@keyframes blink {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

.commit-day {
  width: 20px;
  height: 20px;
  margin: 2px;
  background-color: #ffffff;
  border-radius: 3px; /* Optional: to make the corners rounded */
  box-shadow: 0 2px 4px rgba(255, 255, 255, 0.1); /* Adds a soft shadow for depth */
}

.commit-count-0 {
  background-color: #ebedf0;
}

.commit-count-1 {
  background-color: #c6e48b;
}

.commit-count-2 {
  background-color: #7bc96f;
}

.commit-count-3 {
  background-color: #239a3b;
}

.commit-count-4 {
  background-color: #196127;
}

.commit-day-blink {
  animation: blink 1.5s infinite;
}
</style>
