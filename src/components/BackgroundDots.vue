<template>
  <div class="background-dots">
    <div class="dots"></div>
  </div>
</template>

<script>
export default {
  name: 'BackgroundDots'
};
</script>

<style scoped>
.background-dots {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  z-index: -1; /* Place the dots behind other content */
}

.dots {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: radial-gradient(circle, rgba(0, 0, 0, 0.1) 1px, transparent 1px);
  background-size: 10px 10px;
  opacity: 0.2; /* Adjust opacity for a subtler effect */
}
</style>
