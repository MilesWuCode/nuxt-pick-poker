<script setup lang="ts">
const selectIndex = ref(0);
</script>

<template>
  <div class="border border-red-500 w-300 h-150 relative wrapper">
    <PickPokerCard
      v-for="i of 9"
      :key="i"
      class="card"
      :class="{ selected: selectIndex === i }"
      @click="selectIndex = i"
    />
  </div>
</template>

<style lang="css" scoped>
.wrapper {
  /*
    您可以在這裡調整扇形的樣式：
    --fan-radius: 調整扇形的曲度。值越大，弧度越平緩。
    --angle-per-card: 每張卡片之間的夾角。
    --card-offset-y: 調整整個扇形的垂直位置。
  */
  --fan-radius: 100rem;
  --angle-per-card: 4deg;
  --card-offset-y: 6rem;
  --card-scale: 1;

  .card {
    position: absolute;
    bottom: var(--card-offset-y);
    left: 50%; /* Added to center the card horizontally */
    transform-origin: 50% var(--fan-radius);
    transition: all 0.25s;

    &:hover {
      bottom: 10rem;
    }

    &:nth-child(1) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(-4 * var(--angle-per-card)));
      z-index: 0;
    }
    &:nth-child(2) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(-3 * var(--angle-per-card)));
      z-index: 1;
    }
    &:nth-child(3) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(-2 * var(--angle-per-card)));
      z-index: 2;
    }
    &:nth-child(4) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(-1 * var(--angle-per-card)));
      z-index: 3;
    }
    &:nth-child(5) {
      transform: translateX(-50%) scale(var(--card-scale)) rotate(0deg);
      z-index: 4;
    }
    &:nth-child(6) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(var(--angle-per-card));
      z-index: 5;
    }
    &:nth-child(7) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(2 * var(--angle-per-card)));
      z-index: 6;
    }
    &:nth-child(8) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(3 * var(--angle-per-card)));
      z-index: 7;
    }
    &:nth-child(9) {
      transform: translateX(-50%) scale(var(--card-scale))
        rotate(calc(4 * var(--angle-per-card)));
      z-index: 8;
    }

    &.selected {
      transform: translateX(-50%) rotate(0);
      left: 50%;
      bottom: 0;
      width: 420px;
      height: 600px;
      z-index: 10;
      &:hover {
        bottom: 0;
      }
    }
  }
}

@media (max-width: 1024px) {
  .wrapper {
    zoom: 0.6;
  }
}

/* RWD for Tablet */
@media (max-width: 768px) {
  .wrapper {
    zoom: 0.6;
  }
}

/* RWD for Mobile */
@media (max-width: 640px) {
  .wrapper {
    zoom: 0.3;
  }
}
</style>
