<template>
  <div class="keypad">
    <div class="keypad-row">
      <button class="keypad-button" v-for="n in 3" :key="n">{{ n }}</button>
    </div>
    <div class="keypad-row">
      <button class="keypad-button" v-for="n in 3" :key="n + 3">
        {{ n + 3 }}
      </button>
    </div>
    <div class="keypad-row">
      <button class="keypad-button" v-for="n in 3" :key="n + 6">
        {{ n + 6 }}
      </button>
    </div>
    <div class="keypad-row">
      <button class="keypad-button">,</button>
      <button class="keypad-button">0</button>
      <button class="keypad-button keypad-button--backspace">
        <img
          src="https://cdn.builder.io/api/v1/image/assets/TEMP/89becf40a3bf7b4b90f9d58560ee4d7ff618bcafcbe79dcf0413b2dd37b0ac92?placeholderIfAbsent=true&apiKey=67300942ed1b4d84acfc771d0a5e8d36"
          alt="Backspace"
          class="backspace-icon"
        />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Keypad',
};
</script>

<style scoped>
.keypad {
  background-color: #fff;
  padding: 24px 0;
}

.keypad-row {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-bottom: 24px;
}

.keypad-button {
  width: 60px;
  height: 60px;
  font-size: 24px;
  font-weight: 500;
  color: #000;
  background: none;
  border: none;
  cursor: pointer;
}

.keypad-button--backspace {
  display: flex;
  justify-content: center;
  align-items: center;
}

.backspace-icon {
  width: 48px;
  height: 24px;
}
</style>
