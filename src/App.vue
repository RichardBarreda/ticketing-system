<template>
  <TicketForm></TicketForm>
</template>

<script>
import TicketForm from './views/TicketForm.vue'



export default {
  name: 'App',
  components: {
    TicketForm, 
  }
}
</script>


<style>
@media (max-width: 767.98px) {
  .modal-banner-show {
    overflow: hidden;
  }
}
</style>
