<template>
  <div class="home">
    <h1>Washer Dryer Notifier</h1>
    <div class="row">
      <div @click="washer = !washer">
        <img v-if="washerStatus" src="/img/washing_machine_icon.svg" alt="washing machine">
        <img v-else src="/img/washing_machine_icon_bw.svg" alt="washing machine">
      </div>
      <div @click="dryer = !dryer">
        <img v-if="dryerStatus" src="/img/dryer_icon.svg" alt="dryer" ref="dryer">
        <img v-else src="/img/dryer_icon_bw.svg" alt="dryer">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  props: {
    msg: String
  },
  data() {
    return {
      washer: false,
      dryer: false
    };
  },
  computed: {
    dryerStatus() {
      return this.dryer;
    },
    washerStatus() {
      return this.washer;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.row {
  display: flex;
  align-content: center;
  overflow-x: hidden;

  > div {
    flex: 1 1 auto;

    > img {
      max-width: 100%;
      max-height: 800px;
      width: 100%;
      height: auto;
      min-width: 100px; /*Note the px*/
      min-height: auto;
    }
  }
}

@media screen and (max-width: 720px) {
  .row {
    flex-direction: column;

    > div:first-of-type {
      margin-bottom: 2rem;
    }

    > div {
      > img {
        max-width: 65%;
        max-height: auto;
        width: 65%;
        height: auto;
        min-width: 100px; /*Note the px*/
        min-height: auto;
      }
    }
  }
}
</style>
