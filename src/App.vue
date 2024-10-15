<template>
  <div class="mobile-payment-app">
    <header class="favorites-section">
      <h2 class="favorites-title">Favoritter</h2>
      <nav class="user-favorites">
        <UserFavorite initials="KJ" firstName="Kaltrine" lastName="Jupa" />
        <UserFavorite initials="LM" firstName="Lærke" lastName="Krejberg..." />
        <UserFavorite initials="EC" firstName="Emma" lastName="Claydon-..." />
      </nav>
    </header>
    <main>
      <section class="amount-display">
        <div class="amount">
          <span class="amount-value">0</span>
          <span class="currency">kr.</span>
        </div>
        <div class="currency-icon">
          <img
            src="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/currency-icon.png"
            alt="Currency icon"
            class="icon"
          />
        </div>
      </section>
      <section class="action-buttons">
        <ActionButton
          type="send"
          icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/send-icon.png"
          text="Send"
        />
        <ActionButton
          type="request"
          icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/request-icon.png"
          text="Anmod"
        />
        <ActionButton
          type="scan"
          icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/scan-icon.png"
          text="Scan"
        />
      </section>
      <Keypad />
      <button class="next-button">Næste</button>
    </main>
    <footer class="app-navigation">
      <NavItem
        icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/home-icon.png"
        text="Hjem"
        :active="true"
      />
      <NavItem
        icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/activities-icon.png"
        text="Aktiviteter"
      />
      <NavItem
        icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/groups-icon.png"
        text="Grupper"
      />
      <NavItem
        icon="https://stackblitz.com/files/vue-vvxnwm/github/Joyful-Jasper/vue-vvxnwm/main/src/assets/profile-icon.png"
        text="Profil"
      />
    </footer>
  </div>
</template>

<script>
import UserFavorite from './components/UserFavorite.vue';
import ActionButton from './components/ActionButton.vue';
import Keypad from './components/Keypad.vue';
import NavItem from './components/NavItem.vue';

export default {
  name: 'MobilePaymentApp',
  components: {
    UserFavorite,
    ActionButton,
    Keypad,
    NavItem,
  },
};
</script>

<style scoped>
.mobile-payment-app {
  background-color: #f5f4f2;
  display: flex;
  max-width: 480px;
  width: 100%;
  padding-top: 48px;
  flex-direction: column;
  overflow: hidden;
  margin: 0 auto;
  font-family: Roboto, sans-serif;
}

.favorites-section {
  padding: 0 24px;
}

.favorites-title {
  font-size: 20px;
  font-weight: 500;
  color: #000;
  margin-bottom: 8px;
}

.user-favorites {
  display: flex;
  justify-content: space-between;
  background-color: #fff;
  border-radius: 16px;
  padding: 22px 24px;
}

.amount-display {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding: 72px 24px;
}

.amount {
  display: flex;
  align-items: center;
  font-size: 64px;
  font-weight: 500;
}

.currency {
  margin-left: 8px;
}

.currency-icon {
  margin-left: 64px;
}

.icon {
  width: 40px;
  height: 40px;
}

.action-buttons {
  display: flex;
  justify-content: center;
  padding: 0 24px;
}

.next-button {
  background-color: #c6c6cb;
  color: #fff;
  border: none;
  border-radius: 0 0 16px 16px;
  padding: 15px 36px;
  font-size: 16px;
  width: 340px;
  max-width: 100%;
  margin: 0 auto;
  cursor: pointer;
}

.app-navigation {
  display: flex;
  justify-content: center;
  padding: 12px 24px;
  gap: 56px;
}
</style>
