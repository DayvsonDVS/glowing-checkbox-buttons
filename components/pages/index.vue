<template>
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css"
    integrity="sha512-MV7K8+y+gLIBoVD59lQIYicR65iaqukzvf/nwasF0nqhPay5w/9lJmVM2hMDcnK1OnMGCdVK+iQrJ7lzPJQd1w=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  />
  <div class="buttons">
    <label v-for="icon in list">
      <input type="checkbox" name="check" />
      <span></span>
      <li :class="icon"></li>
    </label>
  </div>
</template>

<script setup lang="ts">
import 'assets/scss/main.scss'

const list = [
  'fa-solid fa-phone',
  'fa-solid fa-plane',
  'fa-solid fa-moon',
  'fa-solid fa-wifi',
  'fa-solid fa-volume-xmark',
  'fa-brands fa-bluetooth-b'
]
</script>

<style scoped lang="scss">
.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  max-width: 140px;
  gap: 20px;
  label {
    position: relative;
    width: 60px;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    input {
      appearance: none;
      &:checked ~ span {
        box-shadow: inset 0 2px 2px rgba(0, 0, 0, 0.35),
          inset 0 5px 5px rgba(0, 0, 0, 0.5),
          inset 0 15px 25px rgba(0, 0, 0, 0.35);
      }
      &:checked ~ li {
        color: #fff;
        text-shadow: 0 0 5px #219cf3, 0 0 8px #219cf3;
      }
    }
    span {
      position: absolute;
      width: 100%;
      height: 100%;
      background: linear-gradient(#555353, #363535, #303030);
      border: 2px solid #222;
      border-radius: 6px;
      box-shadow: inset 0 5px 1px rgba(0, 0, 0, 0.35),
        0 5px 5px rgba(0, 0, 0, 0.5), 0 15px 25px rgba(0, 0, 0, 0.35);
      &::before {
        content: '';
        position: absolute;
        inset: 5px 3px;
        border-top: 1px solid #ccc;
        filter: blur(2px);
      }
    }
    li {
      position: relative;
      z-index: 10;
      font-size: 1.5em;
      color: #111;
    }
  }
}
</style>
