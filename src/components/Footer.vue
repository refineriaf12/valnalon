<template>
  <div>
    <figure>
      <img src="@/assets/logos/logo_lila.svg" alt="" />
    </figure>
    <figure>
      <img src="@/assets/logos/logo_valnalon vector.svg" alt="" />
    </figure>
    <figure>
      <img src="@/assets/logos/logo_vector Principado.svg" alt="" />
    </figure>
  </div>
</template>

<style scoped>
div {
  height: 80px;
  border-top: 6px solid #9e51ff;
  display: flex;
  justify-content: space-evenly;
  align-content: space-around;
  align-items: center;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
}
figure {
  width: 80px;
  height: 80px;
  display: flex;
  align-content: center;
}
img {
  width: 100%;
}
</style>
