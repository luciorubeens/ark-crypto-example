<template>
  <main>
    <h2>Address from window object</h2>
    <p>{{address}}</p>
    <h2>Balance from module</h2>
    <p>{{balance}}</p>
  </main>
</template>

<script>
import {Utils} from "../crypto.bundled";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  },
  computed: {
    address() {
      return window.ArkCrypto.Identities.Address.fromPassphrase("ark")
    },
    balance() {
      return Utils.BigNumber.make(1).plus(1e9).toFixed();
    }
  }
}
</script>
