<template>
  <header class="wrapper-header">
    <section class="desktop-header">
      <nav class="menu">
        <div class="menu__item">
          <a href="/fighters">
            fighters
          </a>
        </div>
        <div class="menu__item">
          <a href="#">
            Раздел
          </a>
        </div>
        <div class="menu__item">
          <a href="#">
            Раздел
          </a>
        </div>
      </nav>
      <nav class="menu menu_show">
        <div class="menu__logo">
          <img src="/logo_black.png" alt="itstime">
        </div>
      </nav>
      <nav class="menu">
        <div class="menu__item">
          <a href="#">
            Раздел
          </a>
        </div>
        <div class="menu__item">
          <a href="#">
            Раздел
          </a>
        </div>
        <div class="menu__item">
          <a href="#">
            Раздел
          </a>
        </div>
      </nav>
    </section>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="less" scoped>
.wrapper-header {
  border-bottom: 1px solid #d20a0a;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

.desktop-header,
.mobile-header {
  text-transform: uppercase;
  width: 100%;
}

.desktop-header {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
}

.mobile-header {
  display: none; /* flex; */
  flex-flow: row nowrap;
  justify-content: center;
  position: relative;
  z-index: 3;
}

&__item_active {
  a {
    border-bottom: 5px solid #d20a0a;
  }
}

.menu {
  display: flex;
  align-items: center;
  margin-left: 18px;
  margin-right: 18px;

  a {
    color: black;
    padding-bottom: 25px;
    text-decoration: none;
  }

  a:hover {
    border-bottom: 5px solid #d20a0a;
    color: #d20a0a;
  }

  &__item {
    a:visited {
      color: #d20a0a;
    }

    a:active {
      color: #d20a0a;
    }
  }

  &__item,
  &__logo,
  &__toggle {
    padding: 18px;
  }

  &__item_style-01 {
    width: 100%;
    text-align: center;
    border-top: 1px solid #ededed;
    line-height: 2em;

    a:hover {
      border: none;
    }
  }

  &__item_font-01 {
    font-weight: normal;
  }

  &__logo {
    margin: 0 15px;

    img {
      min-width: 140px;
    }
  }

  &__toggle {
    position: relative;
    margin: 0 30px;
    padding: 0;
    width: 35px;
    height: 35px;

    .toggle-mobile {
      span,
      span::after,
      span::before { /* задаем линии свеху, по центру, снизу */
        position: absolute;
        content: '';
        height: 3px; /* высота линии */
        width: 35px; /* ширина линии */
        background: #d20a0a; /* цвет линии */
        border-radius: 2px;
        cursor: pointer;
      }

      span::before { /* сверху линия (центр. линия вверх) */
        top: -10px;
      }

      span::after { /* снизу линия (центр. линия вниз) */
        bottom: -10px;
      }

      height: 100%;
      position: relative;

      &__button { /* оболочка переключателя */
        position: absolute;
        width: 35px;
        height: 35px;
        padding: 0;
        display: flex;
        align-items: center;

        a {
          display: block; /* заполнение блока обертки ссылкой */
          position: absolute;
          z-index: 2; /* позиция заполненной ссылки "поверх всех" для кликабельности по всей кнопке */
          cursor: pointer;
        }
      }

      /* трансформация при клике */
      &__button span,
      span::after,
      span::before {
        transition: all 500ms ease-in-out;
      }

      /* Центральный блок делаем прозрачным */
      &__button.active span {
        background-color: transparent;
      }

      /* Смещаем псевдо-элементы в центр иконки (на место основного блока) */
      &__button.active span::before,
      &__button.active span::after {
        top: 0;
      }

      /* Наклоняем псевдо-элементы под углом 45 градусов, но в разные стороны */
      &__button.active span::before {
        transform: rotate(45deg);
      }

      &__button.active span::after {
        transform: rotate(-45deg);
      }
    }
  }
}

.menu_location-01 {
  flex-direction: column;
  align-items: center;
}

.menu_show-toggle {
  display: none;

  a:hover {
    border: none;
  }
}

@media screen and (max-width: 1060px) {
  .desktop-header {
    .menu {
      display: none;
    }

    .menu_show,
    .menu_show-toggle {
      display: flex;
    }
  }
}

</style>
