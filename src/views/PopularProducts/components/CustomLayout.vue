<template>
  <div class="custom-layout">
    <slot name="track" />
    <div class="custom-layout__indicator">
      <slot name="indicator" />
    </div>
    <div class="custom-layout-arrows">
      <div
        class="custom-layout-arrows__arrow custom-layout-arrows__arrow_left"
        @click="onMove(-1)"
      >
        <img
          src="@/assets/img/left-arrow.svg"
        />
      </div>
      <div 
        class="custom-layout-arrows__arrow custom-layout-arrows__arrow_right"
        @click="onMove(1)"
      >
        <img
          src="@/assets/img/right-arrow.svg"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  onMove: {
    type: Function,
    required: true,
  },
  disabledSide: {
    type: String,
    required: true,
  },
  currentItem: {
    type: Number,
    required: true,
  },
  items: {
    type: Array,
    required: true,
  },
})
</script>

<style lang="scss" scoped>

.custom-layout {
  &__indicator {
    margin-top: 38px;
    padding: 0 150px;

    :deep(.gsc-indicator) {
      .gsc-indicator {
        &__bar {
          height: 12px;
        }
        &__track {
          height: 5px;
        }
      }
    }
  }

  .custom-layout-arrows {
    display: flex;
    justify-content: flex-end;
    padding: 0 150px;
    gap: 0 24px;

    &__arrow {
      width: 40px;
      height: 40px;
      border-radius: 100px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: transform .2s ease-in-out;

      &:hover {
        transform: scale(1.1, 1.1);
      }

      &_left {
        background: #E0EFF6;
      }

      &_right {
        background: #F9D9DA;
      }
    }
  }
}

@media (max-width: 900px) {
  .custom-layout {
    &__indicator {
      margin-top: 87px;
      padding: 0 20px;
    }

    .custom-layout-arrows {
      display: none;
    }
  }
}

@media (max-width: 600px) {
  .custom-layout {
    &__indicator {
      margin-top: 44px;
      padding: 0 16px;
    }
  }
}
</style>