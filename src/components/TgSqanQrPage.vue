<template>
  <div class="qr-scan-page">
    <h1>Scan Result</h1>
    <h2>{{scanResult.value}}</h2>
    <s>{{params.value}}</s>
    <button @click="handleScanQR">SCAN QR</button>
  </div>
</template>>

<script>
import {ref} from "vue";

export default {
  setup() {
    const scanResult = ref("")
    const  params = ref([])
    return {scanResult, params}
  },
  methods: {
    handleScanQR() {
      console.log('QR code scan initiated');
      window.Telegram.WebApp.showScanQrPopup({"text": "Scan any QR"}, (params) => {
        console.log(params)
        this.params.value = params
        this.scanResult.value = params[0]
        return true;
      })
    }
  }
}
</script>