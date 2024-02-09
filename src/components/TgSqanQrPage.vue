<template>
  <div class="qr-scan-page">
    <h1>Scan Result</h1>
    <h2>{{scanResult}}</h2>
    <button @click="handleScanQR">SCAN QR</button>
    <qrcode-vue class="qr" v-if="scanResult" :value="scanResult" :size = 100></qrcode-vue>
  </div>
</template>>

<script>
import QrcodeVue from 'qrcode.vue';

export default {
  components: {
    QrcodeVue
  },
  data() {
    return {
      scanResult: ""
    }
  },
  methods: {
    handleScanQR() {
      console.log('QR code scan initiated');
      // window.Telegram.WebApp.showScanQrPopup({"text": "Scan any QR"}, (data) => {
      //   console.log(data)
      //   this.scanResult = data
      //   return true;
      // })
      this.scanResult = "123"
    }
  }
}
</script>

<style scoped>
.qr-scan-page {
  display: block;
}
</style>