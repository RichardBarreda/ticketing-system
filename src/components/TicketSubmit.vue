<template>
    <div class="form-wrapper">
        <p class="form-title">{{titleTicketStatus}}</p>

        <div class="input-form-group">
            <div class="form-group-holder">
                <label for="inputFirstName" class="form-label">First Name</label>
                <input type="text" class="form-control" id="inputFirstName" v-model="firstName" :class="{inputError:firstNameIsError}" @blur="checkFirstName">
                <div class="error-backdrop" :class="{errorHidden:firstNameIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
            </div>
    
            <div class="form-group-holder last-form-label">
                <label for="inputLastName" class="form-label">Last Name</label>
                <input type="text" class="form-control" id="inputLastName" v-model="lastName" :class="{inputError:lastNameIsError}" @blur="checkLastName">
                <div class="error-backdrop" :class="{errorHidden:lastNameIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
            </div>
        </div>

        <div class="input-form-group">
            <div class="form-group-holder">
                <label for="inputEmployeeID" class="form-label">Employee ID</label>
                <input type="text" class="form-control" id="inputEmployeeID" v-model="employeeID" :class="{inputError:employeeIDIsError}" @blur="checkEmployeeID">
                <div class="error-backdrop" :class="{errorHidden:employeeIDIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
            </div>
    
            <div class="form-group-holder last-form-label">
                <label for="inputContactNumber" class="form-label">Contact Number</label>
                <input type="text" class="form-control" id="inputContactNumber" v-model="contactNumber" :class="{inputError:contactNumberIsError}" @blur="checkContactNumber">
                <div class="error-backdrop" :class="{errorHidden:contactNumberIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
            </div>
        </div>

        <div class="form-group-holder">
            <label for="inputRequestType" class="form-label">Request Type</label>
            <select class="form-select" id="inputRequestType" v-model="requestType" :class="{inputError:requestTypeIsError}" @blur="checkRequestType">
                <option selected></option>
                <option value="1">Software Installation</option>
                <option value="2">Hardware Installation</option>
                <option value="3">Reset Password</option>
                <option value="4">Virus Scanning</option>
                <option value="5">Network Incident</option>
                <option value="6">Others</option>
            </select>
            <div class="error-backdrop" :class="{errorHidden:requestTypeIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
        </div>

        <div class="form-group-holder">
            <label for="inputRequestItem" class="form-label">Request Item</label>
            <input type="text" class="form-control" id="inputRequestItem" v-model="requestItem" :class="{inputError:requestItemIsError}" @blur="checkRequestItem">
            <div class="error-backdrop" :class="{errorHidden:requestItemIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
        </div>

        <div class="form-group-holder">
            <label for="inputDeviceName" class="form-label">Device Name</label>
            <input type="text" class="form-control" id="inputDeviceName" v-model="deviceName" :class="{inputError:deviceNameIsError}" @blur="checkDeviceName">
            <div class="error-backdrop" :class="{errorHidden:deviceNameIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
        </div>

        <div class="form-group-holder">
            <label for="inputRequestDetails" class="form-label">Request Details</label>
            <textarea class="form-control form-textarea" rows="4" type="text" id="itFormRequestDetails" name="request_details" v-model="requestDetails" :class="{inputError:requestDetailsIsError}" @blur="checkRequestDetails"></textarea>
            <div class="error-backdrop" :class="{errorHidden:requestDetailsIsError}"> INVALID <i class="bi bi-info-circle-fill"></i> </div>
        </div>

        <div class="form-group-holder form-warning" :class="{errorHidden:showError}">
            <div class="warning-group">
                <img class="img-fluid warning-image" :src="warningLogo">
                <p class="warning-text">An input field is incomplete or invalid. Kindly fill up all the required details on the form in order to submit a ticket. Thank you! </p>
            </div>
        </div>

        <div class="form-group-holder">
            <button type="button" class="btn btn-primary ticket-submit-btn" id="disableBtn" @click="checkAllError">SUBMIT</button>
        </div>


    </div>
</template>
  



<script>
  export default {
    name: 'TicketSubmit',
    data() {
        return {
            titleTicketStatus: "Submit Ticket",
            warningLogo: require('../assets/info.png'),

            firstName: "",
            firstNameIsError:false,

            lastName: "",
            lastNameIsError:false,

            employeeID: "",
            employeeIDIsError:false,

            contactNumber: "",
            contactNumberIsError:false,

            requestType: "",
            requestTypeIsError:false,

            requestItem: "",
            requestItemIsError:false,

            deviceName: "",
            deviceNameIsError:false,

            requestDetails: "",
            requestDetailsIsError:false,

            showError: false,
        }
    },
    methods: {
        checkFirstName() {
            if(this.firstName==""){
               this.firstNameIsError = true;
            } else {
                this.firstNameIsError = false;
                
            }
            
            
        },

        checkLastName() {
            if(this.lastName==""){
               this.lastNameIsError = true;
            } else {
                this.lastNameIsError = false;
            }

            
        },

        checkEmployeeID() {
            if(this.employeeID==""){
               this.employeeIDIsError = true;
            } else {
                this.employeeIDIsError = false;
            }

            
        },

        checkContactNumber() {
            if(this.contactNumber==""){
               this.contactNumberIsError = true;
            } else {
                this.contactNumberIsError = false;
            }

            
        },

        checkRequestType() {
            if(this.requestType==""){
               this.requestTypeIsError = true;
            } else {
                this.requestTypeIsError = false;
            }

            
        },

        checkRequestItem() {
            if(this.requestItem==""){
               this.requestItemIsError = true;
            } else {
                this.requestItemIsError = false;
            }

            
        },

        checkDeviceName() {
            if(this.deviceName==""){
               this.deviceNameIsError = true;
            } else {
                this.deviceNameIsError = false;
            }

            
        },

        checkRequestDetails() {
            if(this.requestDetails==""){
               this.requestDetailsIsError = true;
            } else {
                this.requestDetailsIsError = false;
            }

            // this.checkAllError()
        },

        checkAllError() {
            if(this.firstName=="" || this.lastName=="" || this.employeeID=="" || this.contactNumber=="" || this.requestType=="" || this.requestItem=="" || this.deviceName=="" || this.requestDetails=="") {
                this.showError = true;
                this.checkFirstName();
                this.checkLastName();
                this.checkEmployeeID();
                this.checkContactNumber();
                this.checkRequestType();
                this.checkRequestItem();
                this.checkDeviceName();
                this.checkRequestDetails()
            } else {
                this.showError = false;
            }
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
    
    .last-form-label {
        padding-left: 10px;
    }

    .form-group-holder {
        margin-bottom: 5px;
        width: 100%;
        position: relative;
    }

    .form-textarea {
        resize: none;
    }

    .ticket-submit-btn {
        width: 100%;
        margin-top: 15px;
        background-color: #563d7c;
        border-color: #563d7c;
    }

    .ticket-submit-btn:hover {
        background-color: transparent;
        border-color: #563d7c;
        color: #563d7c;
    }

    .warning-group {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 10px 15px;
        border: solid 1px red;
        margin-top: 15px;
        border-radius: 5px;
    }

    .warning-image {
        max-width: 35px;
        margin-right: 15px;
    }

    .warning-text {
        margin: 0px;
        font-size: 12px;
        color: red;
    }

    .inputError {
        background-color: #ff000014;
        border-color: red;
    }

    .errorHidden {
        display: flex!important;
        justify-content: center;
        align-items: center;
    }

    .form-warning {
        display: none;
    }

    .error-backdrop {
        position: absolute;
        top: 49%;
        right: 12px;
        color: red;
        display: none;
        font-size: 12px;
    }

    .bi-info-circle-fill {
        font-size: 18px;
        margin-left: 5px;
    }


    @media (max-width: 767.98px) {
        .input-form-group {
            flex-direction: column;
        }

        .last-form-label {
            padding-left: 0px;
        }
    }

</style>
  