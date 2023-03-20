<template>
  <section class="intro-section">

    <div class="intro-content">
      <h2 class="intro-content__title">
        Exclusive Deals of Furniture Collection
      </h2>

      <span class="intro-content__secondary-text">Explore different categories. Find the best deals.</span>

      <button class="intro-content__btn">
        Shop Now
      </button>
    </div>

  </section>
</template>

<style lang="scss" scoped>
.intro-section {
  background-image: url('@/assets/img/hutomo-abrianto.png');
  background-repeat: no-repeat;
  background-size: cover;
  color: #07484A;
  background-position: 50%;

  .intro-content {
    display: flex;
    flex-direction: column;
    align-items: baseline;
    padding: 334px 0 354px 150px;
    
    &__title {
      width: 700px;
      font-family: 'Playfair Display';
      font-weight: 700;
      font-size: 65px;
      line-height: 85px;
      margin-bottom: 54px;
    }

    &__secondary-text {
      font-family: 'Open Sans';
      font-weight: 400;
      font-size: 24px;
      line-height: 33px;
      margin-bottom: 54px;
    }

    &__btn {
      color: #FFF;
      background: #70908B;
      border-radius: 10px;
      padding: 24px 54px;
      font-family: 'Open Sans';
      font-weight: 700;
      font-size: 24px;
      line-height: 33px;
    }
  }
}

@media (max-width: 900px) {
  .intro-section {
    .intro-content {
      padding: 176px 0 176px 20px;

      &__title {
        width: 500px;
        font-size: 48px;
        line-height: 62px;
        margin-bottom: 16px;
      }

      &__secondary-text {
        font-size: 24px;
        line-height: 33px;
        margin-bottom: 52px;
      }
    }
  }
}

@media (max-width: 600px) {
  .intro-section {
    .intro-content {
      padding: 232px 0 176px 20px;
      align-items: center;

      &__title {
        width: auto;
        font-size: 36px;
        line-height: 52px;
        text-align: center;
      }

      &__secondary-text {
        text-align: center;
        font-size: 18px;
        line-height: 23px;
      }

      &__btn {
        border-radius: 10px;
        padding: 20px 40px;
        font-size: 18px;
        line-height: 23px;
      }
    }
  }
}

@media (max-width: 450px) {
  .intro-section {
    background-position: 20%;
  }
}
</style>