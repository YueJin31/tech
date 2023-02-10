<template>
  <div class="accordeon__item" :class="{ active: isActive }" @click="toggleAccordion">
    <div class="accordeon__item-title">{{ title }}</div>
    <Transition>
      <div v-show="isOpen" class="accordeon__item-body">
        <slot></slot>
      </div>
    </Transition>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
  data: () => ({
    isOpen: false,
    isActive: false,
  }),
  methods: {
    toggleAccordion() {
      this.isOpen = !this.isOpen;
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style lang="scss">
.accordeon {
  background: #ffffff;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.02), 0px 4px 17px rgba(0, 0, 0, 0.14), 0px 4px 22px rgba(0, 0, 0, 0.12);
  border-radius: 8px;
  width: 600px;

  &:last-child {
    border: none;
  }

  .accordeon__item.active {
    background: #faf8f6;
    transition: all 0.5s ease;

    .accordeon__item-title {
      color: #2b41b7;

      &::after {
        transform: rotate(315deg);
        margin-top: 10px;
      }
    }
  }

  &__item {
    padding: 16px 23px 16px;
    border-bottom: 1px solid #d0dbf1;
    cursor: pointer;

    @media screen and (min-width: 768px) {
      padding: 24px 31px 24px;
    }

    &-title {
      color: #0d2a54;
      font-size: 16px;
      font-weight: 800;
      line-height: 24px;
      display: flex;
      justify-content: space-between;

      &::after {
        content: "";
        width: 10px;
        height: 10px;
        border-top: 2px solid #0d2a54;
        border-right: 2px solid #0d2a54;
        display: block;
        transform: rotate(135deg);
        transition: all 0.5s ease;
      }
    }

    &-body {
      font-size: 16px;
      color: #0d2a54;
    }
  }
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>
