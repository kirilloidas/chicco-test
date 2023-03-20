<template>
  <header class="header">

    <img
      class="header__logo-icon"
      src="@/assets/img/logo.svg"
      alt="Logo"
    />

    <nav class="header-menu">

      <button 
        class="header-menu__toggle-btn"
        @click="toggleMenuShow"
      >
        <img
          class="header-menu__toggle-img"
          src="@/assets/img/menu.svg"
        />
      </button>

      <ul 
        class="header-menu__list"
        :class="{'hide-menu': !showMenu}"
      >
        <li 
          class="header-menu__item"
          v-for="item of links"
          :key="item.name"
        >
          <a 
            class="header-menu__link"
            :href="item.href"
          >
            {{ item.name }}
          </a>
        </li>
      </ul>
    </nav>

    <div class="header-icons-block">
      <a 
        class="header-icons-block__link"
        v-for="item of icons"
        :key="item.path"
        href="#"
      >
        <img
          class="header-icons-block__icon"
          :src="item.path"
          :alt="item.alt" 
        />
      </a>
    </div>

  </header>
</template>

<script setup>
import { ref } from 'vue';


const showMenu = ref(false)

const links = [
  {
    name: 'Home',
    href: '#'
  },
  {
    name: 'Products',
    href: '#'
  },
  {
    name: 'Categories',
    href: '#'
  },
  {
    name: 'About',
    href: '#'
  },
  {
    name: 'Contact Us',
    href: '#'
  },
]

const icons = [
  {
    path: new URL('/src/assets/img/search.svg', import.meta.url),
    alt: 'Search'
  },
  {
    path: new URL('/src/assets/img/basket.svg', import.meta.url),
    alt: 'Basket'
  },
  {
    path: new URL('/src/assets/img/user-profile.svg', import.meta.url),
    alt: 'User profile'
  } 
]

const toggleMenuShow = () => showMenu.value = !showMenu.value
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  padding: 26px 150px 38px 150px;
  background: rgba(224, 246, 241, 0.5);

  .header-menu {
    position: relative;

    &__toggle-btn {
      display: none;
      background: inherit;
    }

    &__list {
      display: flex;
    }

    &__item {
      &:not(:last-child) {
        margin-right: 47px;
      }
    }

    &__link {
      position: relative;
      font-family: 'Playfair Display';
      font-weight: 400;
      font-size: 20px;
      line-height: 132.9%;
      letter-spacing: 0.05em;
      color: #07484A;

      &::after {
        content: '';
        position: absolute;
        bottom: -2px;
        left: 0;
        width: 0;
        height: 3px;
        background: #07484A;
        transition: width .2s ease-in-out;
      }

      &:hover {
        font-weight: 700;
        &::after {
          width: 100%;
        }
      }
    }
  }

  .header-icons-block {
    display: flex;

    &__link {
      cursor: pointer;

      &:not(:last-child) {
        margin-right: 58px;
      }
    }
  }
}

@media (max-width: 1300px) {
  .header {
    .header-menu {
      &__toggle-btn {
        display: block;
      }

      &__list {
        display: flex;
        flex-direction: column;
        position: absolute;
        top: 71px;
        left: 0;
        transform: translateX(calc(-25% - 16px));
        padding: 15px;
        background: rgba(224, 246, 241, 0.5);
        gap: 10px 0;

        &.hide-menu {
          display: none;
        }
      }
    }
  }
}

@media (max-width: 980px) {
  .header {
    padding: 26px 20px 38px 20px;
  }
}

@media (max-width: 600px) {
  .header {
    &__logo-icon {
      order: 2;
    }
    .header-menu {
      order: 1;

      &__list {
        transform: translateX(0);
      }
    }

    .header-icons-block {
      order: 3;

      &__link {

        &:not(:last-child) {
          margin-right: 12px;
        }
      }
    }
  }
}
</style>