<template>
    <div class="form-wrapper">
        <p class="form-title">{{titleTicketStatus}}</p>
        <div class="form-group-holder">
            <label for="searchTicketNumber" class="form-label">Ticket Number</label>
            <div class="input-form-group">
                <input type="text" class="form-control" id="searchTicketNumber">
                <button type="button" class="btn btn-primary ticket-search-btn" data-bs-toggle="modal" data-bs-target="#searchModal">SEARCH</button>
            </div>
        </div>
    </div>

    <!-- Modal -->
    <div class="modal fade" id="searchModal" tabindex="-1" aria-labelledby="searchModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">

                <div class="modal-header">
                    <div class="header-group">
                        <i class="bi bi-ticket-fill"></i>
                        <p class="modal-title" id="ticketStatusLabel">IT Ticketing System</p>
                    </div>
                    
                </div>
                
                
                <div class="modal-body">
                    <div class="ticket-status-image">
                        <p class="status-label">TICKET STATUS: <span>ON GOING</span></p>
                    </div>
                    <div class="ticket-status-details" :class="{hide:ticketDetailsIsVisible}" id="ticketStatusDetails">
                        <div class="details-holder">
                            <p class="details-label">Ticket Number:</p>
                            <p class="details-info" id="searchTrigger"></p>
                        </div>
                        <div class="details-holder">
                            <p class="details-label">Date Requested:</p>
                            <p class="details-info"></p>
                        </div>
                        <div class="details-holder">
                            <p class="details-label">Requestor Name:</p>
                            <p class="details-info"></p>
                        </div>
                        
                        <div class="details-holder">
                            <p class="details-label">Request Type:</p>
                            <p class="details-info"></p>
                        </div>
                        <div class="details-holder">
                            <p class="details-label">Request Item:</p>
                            <p class="details-info"></p>
                        </div>
                        <div class="details-holder">
                            <p class="details-label">Request Details:</p>
                            <p class="details-info scroll-info">
                                
                            </p>
                        </div>
                    </div>
                    <div class="ticket-status-message">
                        <p class="ticket-message">Your Ticket is now on going. Thank you for your patience, IT Team is doing their best to resolve your concern immediately.</p>
                    </div>
                    <div class="ticket-status-form">
                        <form>
                            <div class="ticket-form-message" :class="{hide:sendMessageIsVisible}" id="hiddenMessageForm">
                                <div class="details-holder no-border-bottom">
                                    <p class="details-label">Ticket Number:</p>
                                    <p class="details-info"></p>
                                </div>
                                <div class="details-holder no-border-bottom">
                                    <p class="details-label">Subject:</p>
                                    <select class="form-control form-subject" id="" name="">
                                        <option></option>
                                        <option>Follow up Request</option>
                                        <option>Cancellation Request</option>
                                        <option>Change in Request Details</option>
                                    </select>
                                </div>
                                <div class="details-holder no-border-bottom">
                                    <p class="details-label">Message:</p>
                                    <textarea  class="form-control form-textarea" rows="6" type="text" id="" name=""> </textarea>
                                </div>
                                
                            </div>
                            <button type="button" class="btn btn-primary ticket-followup-btn" :class="{hide:ticketDetailsIsVisible}" @click="showMessage" id="ticketFollowUpBtn">Send Message</button>              
                            <div class="submit-btn-group" :class="{hide:sendMessageIsVisible}" id="cancelFollowUpBtnGroup">
                                <button type="button" class="btn btn-primary cancel-followup-btn">Submit</button>
                                <button type="button" class="btn btn-primary cancel-followup-btn" @click="hideMessage" id="cancelFollowUpBtn">Cancel</button>    
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>
  



<script>
  export default {
    name: 'TicketStatus',
    data() {
        return {
            titleTicketStatus: "Ticket Status",
            sendMessageIsVisible: true,
            ticketDetailsIsVisible: false,
        }
    },
    methods: {
        showMessage() {
            this.sendMessageIsVisible = false;
            this.ticketDetailsIsVisible = true;
        },

        hideMessage() {
            this.sendMessageIsVisible = true;
            this.ticketDetailsIsVisible = false;
        }
    }
  }
</script>
  



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    .form-wrapper {
        margin-top: 30px;
        margin-bottom: 30px;
        padding: 20px 25px;
        border: solid 1px gainsboro;
        border-radius: 10px;
        background-color: whitesmoke;
    }

    .form-label {
        margin-bottom: 0px;
        font-size: 14px;
    }

    .form-title {
        margin-bottom: 0px;
        font-size: 25px;
        font-weight: 500;
        text-transform: uppercase;
    }

    .input-form-group {
        display: flex;
    }

    .ticket-search-btn {
        width: 100%;
        max-width: 120px;
        background-color: #563d7c;
        border-color: #563d7c;
        margin-left: 10px;
    }

    .ticket-search-btn:hover {
        background-color: transparent;
        border-color: #563d7c;
        color: #563d7c;
    }



    .modal-header {
        background-color: white;
        padding: 0px;
        border-radius: 5px 5px 0px 0px;
    }

    .bi-ticket-fill {
        color: white;
        font-size: 25px;
        margin-left: 10px;
    }

    .ticket-status-image {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .status-label {
        padding: 0px;
        margin: 0px;
        text-align: center;
        font-size: 18px;
        text-transform: uppercase;
        font-weight: 500;
    }

    .ticket-status-details {
        border-top: solid 2px #563d7c;
        margin-top: 5px;
        padding-top: 5px;
    }

    .details-holder {
        padding-bottom: 2px;
        padding-top: 2px;
        line-height: 17px;
        border-bottom: solid 1px gainsboro;
    }

    .no-border-bottom {
        border-bottom: none;
    }

    .form-textarea {
        margin-bottom: 10px;
        resize: none;
        line-height: 20px;
        font-size: 14px;
        padding: 5px 8px;
    }

    .details-label {
        margin: 5px;
        font-size: 12px;
        font-weight: 700;
        text-transform: uppercase;
    }

    .details-info {
        margin: 0px;
        font-size: 15px;
        color: #676e74;
    }

    .scroll-info {
        height: 85px;
        overflow-y: scroll;
    }

    .ticket-status-message {
        border-top: solid 2px #563d7c;
        padding-top: 10px;
    }

    .ticket-message {
        margin: 0px;
        font-size: 13px;
        color: black;
        line-height: 15px;
    }

    .submit-btn-group {
        display: flex;
    }

    .hide {
        display: none!important;
    }

    .cancel-followup-btn {
        width: 100%;
        background-color: #563d7c;
        border-color: #563d7c;
        padding: 3px 0px;
    }

    .cancel-followup-btn:first-child {
        margin-right: 5px;
    }

    .ticket-followup-btn {
        width: 100%;
        background-color: #563d7c;
        border-color: #563d7c;
        padding: 3px 0px;
    }

    .ticket-status-form {
        padding-top: 10px;
    }

    .modal-title {
        color: white;
        text-transform: uppercase;
        font-size: 18px;
        font-weight: 500;
        padding-right: 10px;
    }

    .header-group {
        width: 100%;
        padding: 3px 5px;
        border-radius: 0px;
        background-color: #563d7c;
        margin-top: 15px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }




    @media (max-width: 767.98px) {
        .input-form-group {
            flex-direction: column;
        }

        .ticket-search-btn {
            width: 100%;
            max-width: 100%;
            margin-left: 0px;
            margin-top: 10px;
        }
    }
</style>
  