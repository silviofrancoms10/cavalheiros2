<template>
  <nav class="bottom-nav">
    <a href="https://wa.me/5567991043906" target="_blank" class="nav-btn">
      <span class="material-symbols-outlined">chat</span>
      <span class="nav-text">WHATSAPP</span>
    </a>
    <div class="divider"></div>
    <a href="https://maps.app.goo.gl/x9obhEdqVehWqgfEA" target="_blank" rel="noopener noreferrer" class="nav-btn">
      <span class="material-symbols-outlined">location_on</span>
      <span class="nav-text">LOCALIZAÇÃO</span>
    </a>
  </nav>
</template>

<script setup>
</script>

<style scoped>
.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 64px;
  background-color: var(--color-antique-gold);
  z-index: 100;
  display: flex;
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.2);
}

.nav-btn {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  text-decoration: none;
  color: var(--text-on-gold);
}

.nav-text {
  font-family: 'Montserrat', sans-serif;
  font-weight: 700;
  font-size: 0.8rem;
  letter-spacing: 0.05em;
}

.divider {
  width: 1px;
  height: 60%;
  background-color: rgba(39, 25, 0, 0.2);
  align-self: center;
}

@media (min-width: 769px) {
  .bottom-nav {
    display: none;
  }
}
</style>
