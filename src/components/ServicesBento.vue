<template>
  <section id="servicos" class="services-section">
    <div class="container">
      <div class="services-grid">
        <div class="service-card large">
          <div class="card-image">
            <img src="/assets/massagem.png" alt="Massagem Relaxante" />
          </div>
          <div class="card-content">
            <span class="card-label">MASSAGEM</span>
            <h3 class="card-title">Massagem Relaxante</h3>
          </div>
        </div>

        <div class="service-card vertical">
          <div class="card-image">
            <img src="/assets/pele.png" alt="Limpeza de Pele" />
          </div>
          <div class="card-content">
            <span class="card-label">SKIN CARE</span>
            <h3 class="card-title">Limpeza de Pele Profunda</h3>
          </div>
        </div>

        <div class="service-card medium">
          <div class="card-image">
            <img src="/assets/design-sombrancelha.png" alt="Design / Depilação" />
          </div>
          <div class="card-content">
            <span class="card-label">DESIGN</span>
            <h3 class="card-title">Design</h3>
          </div>
        </div>

        <div class="service-card medium">
          <div class="card-image">
            <img src="/assets/depilacao.webp" alt="Depilação Masculina" />
          </div>
          <div class="card-content">
            <span class="card-label">DEPILAÇÃO</span>
            <h3 class="card-title">Depilação Masculina</h3>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.services-section {
  padding: 100px 0;
  background-color: var(--surface-base);
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--gutter);
}

.service-card {
  background: var(--surface-low);
  border-top: 1px solid rgba(197, 160, 89, 0.2);
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.card-image {
  overflow: hidden;
  width: 100%;
  height: 100%;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.7s ease;
}

.service-card:hover .card-image img {
  transform: scale(1.05);
}

.card-content {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 24px;
  background: linear-gradient(to top, rgba(26, 36, 47, 0.9), transparent);
  z-index: 2;
}

.card-label {
  display: inline-block;
  font-family: 'Montserrat', sans-serif;
  font-size: 0.7rem;
  color: var(--color-antique-gold);
  border: 1px solid rgba(197, 160, 89, 0.4);
  padding: 4px 10px;
  margin-bottom: 12px;
  letter-spacing: 0.1em;
}

.card-title {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  color: var(--text-on-surface);
}

/* Bento Layout */
.large {
  grid-column: span 8;
  aspect-ratio: 16/9;
}

.vertical {
  grid-column: span 4;
  aspect-ratio: 3/4;
}

.medium {
  grid-column: span 6;
  aspect-ratio: 16/9;
}

@media (max-width: 992px) {
  .large, .vertical, .medium {
    grid-column: span 12;
    aspect-ratio: 16/9;
  }
}
</style>
