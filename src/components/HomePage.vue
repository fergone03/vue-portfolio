<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
})
</script>
vx
<template>
  <div class="greetings">
    <h1 class="white">{{ msg }}</h1>
    <h3>
      Desarrollador creativo y entusiasta.
      <span>Desarrollador Web.</span>
      <span> De Granada, España.</span>
      Apasionado por crear soluciones innovadoras, con especial enfoque en Frontend y una sólida
      capacidad para trabajar en Backend.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
