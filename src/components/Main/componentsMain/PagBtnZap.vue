<template>
    <a href="https://web.whatsapp.com/send?phone=88999501040" target="_blank" class="whats">
        <div><img src="/img/icon/iconeFINAL.png" alt="" class="icon"></div>
    </a>
</template>

<script >
    export default {
        name: 'BtnZap'
    }
</script>

<style scoped>
.whats {
  position: fixed;
  width: 3.75rem;
  height: 3.75rem;
  bottom: 2.5rem;
  right: 2.5rem;
  background-color: #25d366;
  border-radius: 3.125rem;
  z-index: 1000;
  box-shadow: 0.063rem 0.063rem 0.188rem;
}

.icon {
  margin-top: 0.938rem;
  margin-left: 0.938rem;
}

@media screen and (max-width: 200px){
  .whats {
    display:none
  }
}
</style>