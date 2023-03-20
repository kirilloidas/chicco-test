<template>
  <div 
    class="carousel-card"
    :style="{
      background: item.cardBgColor,
    }"
  >
    <img
      class="carousel-card__img"
      :src="item.cardImg"
      :alt="item.cardTitle"
    />

    <div class="carousel-card__content">
      <h4 class="carousel-card__title">
        {{ item.cardTitle }}
      </h4>
      <span class="carousel-card__description">
        {{ item.cardDescription }}
      </span>
      <span class="carousel-card__price">
        {{ item.cardPrice }}
      </span>
    </div>
  </div>
</template>

<script setup>
defineProps({
  item: {
    type: Object,
    default: () => {}
  }
})
</script>

<style lang="scss" scoped>
.carousel-card {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
  padding-bottom: 60px;
  border-radius: 16px;
  width: 430px;
  height: 585px;

  &__img {
    max-height: 294px;
  }

  &__content {
    margin-top: 40px;
    display: flex;
    flex-direction: column;
    width: 100%;
    padding-left: 40px;

    & > *{
      color: #70908B;
      font-family: 'Open Sans';
    }
  }

  &__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 36px;
    margin-bottom: 1em;
  }

  &__description {
    font-weight: 400;
    margin-bottom: 1em;
    font-size: 18px;
    line-height: 25px;
  }

  &__price {
    font-weight: 700;
    font-size: 24px;
    line-height: 32px;
  }
}

@media (max-width: 900px) {
  .carousel-card {
    width: 416px;
  }
}

@media (max-width: 600px) {
  .carousel-card {
    width: 237px;
    height: 340px;
    padding-bottom: 20px;

    &__img {
      max-height: 135px;
    }

    &__title {
      font-size: 18px;
      line-height: 23px;
    }
  }
}
</style>