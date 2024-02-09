<template>
  <div class="qr-scan-page">
    <h1>Scan Result</h1>
    <h2>{{scanResult.value}}</h2>
    <label>{{params.value}}</label>
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
      window.Telegram.WebApp.showScanQrPopup({"text": "Scan any QR"}, (data) => {
        console.log(data)
        this.params.value = data
        this.scanResult.value = data
        return true;
      })
    }
  }
}
</script>