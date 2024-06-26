<template>
    <div class="ticket-form-holder">
        <div class="container">
            <div class="content-wrapper">
                <Banner class="hide"></Banner>
                <Form></Form>
            </div>
        </div>
    </div>

    <div class="mobile-modal" :class="{closeModalMobile:modalIsHidden}">
        <Banner @close="toggleModal"></Banner>
    </div>
</template>
  



<script>
import Banner from '@/components/Banner.vue'
import Form from '@/components/Form.vue'
export default {
    name: 'TicketForm',
    components: {
        Banner, Form
    },
    data() {
        return {
            modalIsHidden: false,
        }
    },
    methods: {
        toggleModal() {
            this.modalIsHidden = true;
            document.querySelector('body').classList.remove('modal-banner-show');
        }
    }
}
</script>
  



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.content-wrapper {
    display: flex;
}

.mobile-modal {
    display: none;
}

.ticket-form-holder {
    position: relative;
}

@media (max-width: 767.98px) {
    .content-wrapper {
        flex-direction: column;
        padding: 10px;
    }

    .hide {
        display:none;
    }

    .mobile-modal {
        position: absolute;
        top: 0;
        height: 100vh;
        background-color: #808080e3;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
    }

    .closeModalMobile {
        display: none!important;
    }
}
</style>
  