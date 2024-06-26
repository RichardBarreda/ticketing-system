<template>
    <div class="form-holder">
        <TicketStatus></TicketStatus>
        <TicketSubmit></TicketSubmit>
    </div>
</template>
  



<script>
    import TicketStatus from '@/components/TicketStatus.vue'
    import TicketSubmit from '@/components/TicketSubmit.vue'
    export default {
        name: 'Form',
        components: {
            TicketStatus, TicketSubmit
        },
        data() {
            return {
                titleTicketStatus: "Ticket Status",
            }
        }
    }
</script>
  



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .form-holder {
        width: 100%;
        max-width: 50%;
    }

    @media (max-width: 767.98px) {
        .form-holder {
            max-width: 100%;
        }
    }

    
</style>
  