<template>
  <div id="third-level">
    <component :is="'BackButton'" class="back-button" />
    <h1 class="title">{{ $faq.title }}</h1>
    <div class="content" v-html="$faq.content"></div>
  </div>
</template>

<script>
import BackButton from '../components/BackButton'

export default {
  components: {
    BackButton
  },
  computed: {
    $faq() {
      return this.$store.getters.$faq[0]
    }
  }
}
</script>

<style scoped>
#third-level {
  width: 100%;
  height: 100%;
  display: grid;
  grid: 90px 1fr / 1fr;
  font-family: Lato;
}

.back-button {
  position: absolute;
  margin: 15px 0 0 12px;
}

.title {
  align-self: center;
  justify-self: center;
  width: 50%;
  text-align: left;
  line-height: 1.2rem;
  padding: 20px 0 0 0;
  height: 100%;
  font-weight: 400;
  font-size: 16px;
  color: #f5f6f8;
}

.content {
  height: 100%;
  font-size: 13px;
  color: #f5f6f8;
  line-height: 1.3rem;
  padding: 0 20px;
  letter-spacing: 0.02rem;
}
</style>
