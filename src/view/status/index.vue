<template>
  <app-panel>
    <div class="view-status-text">
      <h2>
        <span>You successfully redeemed your AE!</span>
      </h2>
      <h3>
        Transaction hash: {{ $route.params.hash }}
      </h3>
    </div>
    <ae-button
      face="round"
      fill="primary"
      @click="$router.push({ name: 'redeem' })"
    >
      Redeem another paper wallet
    </ae-button>
  </app-panel>
</template>
<script>
import AeButton from '@aeternity/aepp-components/dist/ae-button'
import AppPanel from '../../components/app-panel'

export default {
  name: 'view-status',
  components: {
    AeButton,
    AppPanel
  },
  mounted() {
    this.$store.commit('setPrivKey', null)
    this.$store.commit('setKeypair', null)
    this.$store.commit('setAddress', null)
  },
}
</script>
<style lang="scss" scoped>
.view-status-text {
  margin-bottom: 3rem;

  > h2 {
    @extend %face-sans-l;

    font-size: rem(23px);
    font-weight: 500;

    span:first-child {
      color: $color-primary;
    }
    span:last-child {
      color: $color-neutral-minimum;
    }
  }

  > h3 {
    @extend %face-sans-base;

    font-size: rem(17px);
    color: $color-neutral-negative-2;
    font-weight: 500;
  }
}
</style>
