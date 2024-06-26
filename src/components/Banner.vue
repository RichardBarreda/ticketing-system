<template>
    <div class="banner-holder">
      <div class="content-wrapper">
        <img class="img-fluid form-logo" :src="logo" />
        <p class="banner-title">{{ title }}</p>
        <p class="banner-noted">{{note}}</p>
        <button type="button" class="btn btn-secondary btn-modal-close" @click="closeModal">Close</button>
      </div>
    </div>
</template>
  



<script>
  export default {
    name: 'Banner',
    data() {
        return {
          logo: require('../assets/ticket-form.png'),
          title: "IT TICKETING SYSTEM",
          note: "Need an IT Support? Kindly submit an online ticket through our ticketing system. For urgent concern you may call us through our local number 1170 and 1171. To check the status of your request, please provide your Ticket Number to check your application status."
        }
    },
    methods: {
      closeModal() {
        this.$emit("close");
      }
    }
  }
</script>
  



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.banner-holder {
  height: 100vh;
  width: 100%;
  max-width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.form-logo {
  max-width: 400px;
}

.banner-title {
  font-size: 30px;
  text-align: center;
  color: white;
  font-weight: 500;
  text-transform: uppercase;
  background: #563d7c;
  width: 100%;
}

.banner-noted {
  width: 450px;
  text-align: center;
  font-size: 11px;
}

.content-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: fixed;
}

.btn-modal-close {
  margin-top: 20px;
  width: 100%;
  display: none;
}

@media (max-width: 767.98px) {
  .banner-holder {
      height: auto;
      max-width: 100%;
      background-color: white;
      padding: 15px;
      border-radius: 10px;
  }

  .btn-modal-close {
    display: block;
  }

  .content-wrapper {
    position: relative;
    max-width: 100%;
    width: 100%;
  }

  .form-logo {
    width: 100%;
  }

  .banner-noted {
    max-width: 100%;
    width: 100%;
  }
}
</style>
  