<template>
  <div 
    class="wrapper"
    :class="{ 'light': !isDark, 'dark': isDark }"
  >
    <div class="wrapper__content">
      <div class="wrapper__buttons">
        <button @click="togglePicture">Switch image</button>
        <button @click="toggleTheme">Switch theme</button>
      </div>

      <div class="wrapper__icons">
        <svg-icon v-if="isDesktop" name="desktopLogo" />
        <svg-icon v-if="!isDesktop" name="phoneLogo" />
      </div>
    </div>
  </div>
</template>

<script>
import SvgIcon from '@/components/SvgIcon'

export default {
  name: 'Page',
  components: {
    SvgIcon
  },
  data: () => ({
    isDesktop: true,
    isDark: false
  }),
  methods: {
    togglePicture () {
      this.isDesktop = !this.isDesktop
    },
    toggleTheme () {
      this.isDark = !this.isDark
    }
  }
}
</script>

<style lang="css">
.wrapper {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
}

.wrapper__content {
  margin: auto 0;
}

.wrapper__icons {
  height: 150px;
  display: flex;
  justify-content: center;
}

.light {
  background: yellow;
  color: rgb(80, 79, 79);
}

.dark {
  background: darkgreen;
  color: rgb(245, 218, 218);
}

.wrapper__buttons {
  display: flex;
  flex-wrap: wrap;
}

button {
  appearance: none;
  background-color: #5d96db;
  border: 1px solid rgba(27, 31, 35, .15);
  border-radius: 6px;
  box-shadow: rgba(27, 31, 35, .1) 0 1px 0;
  box-sizing: border-box;
  color: currentColor;
  cursor: pointer;
  display: inline-block;
  font-family: -apple-system, system-ui, "Segoe UI", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
  font-size: 14px;
  font-weight: 600;
  line-height: 20px;
  padding: 6px 16px;
  position: relative;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: middle;
  white-space: nowrap;

  margin: 5px;
  flex-basis: 100%;
}

</style>
