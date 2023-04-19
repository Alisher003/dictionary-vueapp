<template>
      <!-- HEADER -->
      <header class="header">
        <div class="container">
            <div class="header__wrapper">
                <div class="header__logo">
                    <a href="/">
                        <img src="../assets/img/book-logo.png" alt="logo">
                    </a>
                </div>

                <div class="header__widgets">
                    <div class="header__select">
                        <p class="header__select--selected body-m text-black-2d">
                            Sans Serif
                        </p>
                        <img src="../assets/img/select-icon.png" alt="icon">
                        <div class="header__selectors">
                            <ul>
                                <li>
                                    <p class="body-m text-black-2d">Sans Serif</p>
                                </li>
                                <li>
                                    <p class="body-m text-black-2d">Serif</p>
                                </li>
                                <li>
                                    <p class="body-m text-black-2d">Mono</p>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <span></span>
                    <div class="header__toggle">
                        <!-- <div class="header__toggle__btn"><span></span></div> -->
                        <div
                            class="header__toggle__btn"
                            :class="darkModeToggle ? 'dark' : ''"
                            @click="darkMode"
                            >
                            <span></span>
                        </div>
                        <i class="fa-solid fa-moon"></i>
                    </div>
                </div>
            </div>
        </div>
    </header>

</template>

<script setup>
const darkMode = () => {
  darkModeToggle.value = !darkModeToggle.value;
  document.body.getAttribute("data-theme")
    ? document.body.removeAttribute("data-theme")
    : document.body.setAttribute("data-theme", "dark");
  saveThemeStorage();
};
</script>



<style lang="scss" >
  .header {
    &__wrapper {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-top: 60px;
        margin-bottom: 50px;
    }

  &__widgets {
      display: flex;
      align-items: center;
      gap: 26px;

      & > span {
          height: 32px;
          width: 1px;
          background: var(--gray);
      }
  }

  &__select {
      &.open {

          .header__selectors {
              display: block;
          }

      }

      &ors {
          position: absolute;
          display: none;
          right: 0;
          top: 20px;
          z-index: 2;
          
          ul {
              margin-top: 10px;
              box-shadow: var(--shadow);
              border-radius: var(--radius);
              background: var(--white);
              padding: 16px 24px;
              padding-right: 70px;
              display: flex;
              flex-direction: column;

              p {
                  padding: 8px 0;
                  white-space: nowrap;
                  transition: var(--transition);
                  &:hover {
                      color: var(--purple);
                  }
              }
          }
      }
      
      position: relative;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 18px;

      p {
          font-weight: bold;
      }

  }
  
  &__toggle {
      display: flex;
      align-items: center;
      gap: 20px;

      &__btn {
          width: 40px;
          height: 20px;
          border-radius: 10px;
          background: var(--gray-bold);
          padding: 3px;
          cursor: pointer;
          transition: var(--transition);
          &.dark {
              background: var(--purple);
              span {
                  margin-left: auto;
                  transition: var(--transition);
              }
              & ~ i {
                  color: var(--purple);
              }
          }

          span {
              display: flex;
              width: 14px;
              height: 14px;
              border-radius: 50%;
              background: #fff;
              transition: var(--transition);
          }
      }

      i {
          font-size: 20px;
          background: transparent;
          color: var(--gray-bold);
          transition: var(--transition);
          cursor: pointer;
      }
  }
}


  
</style>