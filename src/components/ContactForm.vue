<template>
    <form @submit.prevent="handleSubmit">
        <h3>Kontakt os</h3>
        <label>Navn</label>
        <input type="userName" required v-model="userName" />
        <div v-if="userNameError">{{ userNameError }}</div>

        <label>Telefonnummer</label>
        <input type="phoneNumber" required v-model="phoneNumber" />
        <div v-if="phoneNumberError">{{ phoneNumberError }}</div>

        <label>Email</label>
        <input type="email" required v-model="email" />

        <label>Besked</label>
        <textarea type="message" required v-model="message"></textarea>
        <div v-if="messageError">{{ messageError }}</div>

        <div class="submit"></div>
        <button class="klik2">Send Besked</button>
    </form>

    <form class="queryform" @submit.prevent="handleSubmit">
        <h3>Kontakt os</h3>
        <label>Navn</label>
        <input type="userName" required v-model="userName" />
        <div v-if="userNameError">{{ userNameError }}</div>

        <label>Telefonnummer</label>
        <input type="phoneNumber" required v-model="phoneNumber" />
        <div v-if="phoneNumberError">{{ phoneNumberError }}</div>

        <label>Email</label>
        <input type="email" required v-model="email" />

        <label>Besked</label>
        <textarea type="message" required v-model="message"></textarea>
        <div v-if="messageError">{{ messageError }}</div>

        <div class="submit"></div>
        <button class="klik2">Send Besked</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            email: "",
            userName: "",
            userNameError: "",
            phoneNumber: "",
            phoneNumberError: "",
            message: "",
            messageError: "",
        };
    },
    methods: {
        handleSubmit() {
            // besked validation (skal have flere)
            (this.userNameError = this.userName.length > 2 ? "" : "Indtast et rigtigt navn "),
                (this.phoneNumberError =
                    this.phoneNumber.length == 8 ? "" : "indtast rigtigt telefon nummer på 8 tal "),
                (this.messageError =
                    this.message.length > 15 ? "" : "vær sød at specificere problemet ");
        },
    },
};
</script>

<style></style>
