<!-- <template>
    <v-sheet width="500" class="contact-form mx-auto">
        <v-form @submit.prevent="submitForm"> 
            <div class="text-input" id="name">
                <label>Name: </label>
                <input type="text" v-model="name" required>
            </div>

            <div class="btn">
                <label style="font-size: 2.5rem;">Best way to contact you</label>
                <br>
                <input type="radio" id="phone" value="phone" v-model="contactMethod">
                <label for="phone" style="font-size: 2rem;"> Phone Number</label>
                <br>
                <input type="radio" id="email" value="email" v-model="contactMethod">
                <label for="email" style="font-size: 2rem"> Email</label>
            </div>

            <div v-if="contactMethod === 'phone'" class="text-input">
                <label>Phone: </label>
                <input type="tel" v-model="phone" required>
            </div>

            <div v-if="contactMethod === 'email'" class="text-input">
                <label>Email: </label>
                <input type="email" v-model="email" required>
            </div>

            <div class="text-input" >
                <label>what it do </label>
                <input type="text" v-model="message" required>
            </div>

            <button id="submit-btn" type="submit">Submit</button>
        </v-form>

    </v-sheet>

</template> -->
<template>
    <v-container class="contact-form bg-gray">

        <form @submit.prevent="submit">
            <v-text-field class="text-black" v-model="name.value.value" :counter="10" :error-messages="name.errorMessage.value"
                label="Name"></v-text-field>

            <v-text-field icon="mdi-phone" v-model="phone.value.value" :counter="7" :error-messages="phone.errorMessage.value"
                label="Phone Number"></v-text-field>

            <v-text-field v-model="email.value.value" :error-messages="email.errorMessage.value"
                label="E-mail"></v-text-field>

            <v-select v-model="select.value.value" :items="items" :error-messages="select.errorMessage.value"
                label="Select"></v-select>

            <v-text-field v-model="text.value.value" :items="items" :error-messages="text.errorMessage.value"
                label="Message"></v-text-field>

            <v-checkbox  v-model="checkbox.value.value" :error-messages="checkbox.errorMessage.value" value="1"
                label="I'm a person I swear (most of the time)" class="text-000000" type="checkbox"></v-checkbox>

            <v-btn class="me-8" type="submit">
                submit
            </v-btn>

            <v-btn @click="handleReset">
                clear
            </v-btn>
        </form>
    </v-container>
</template>
<script setup>
import { ref } from 'vue'
import { useField, useForm } from 'vee-validate'

const { handleSubmit, handleReset } = useForm({
    validationSchema: {
        name(value) {
            if (value?.length >= 2) return true

            return 'Name needs to be at least 2 characters.'
        },
        phone(value) {
            if (value?.length > 9 && /[0-9-]+/.test(value)) return true

            return 'Phone number needs to be at least 9 digits.'
        },
        email(value) {
            if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true

            return 'Must be a valid e-mail.'
        },
        select(value) {
            if (value) return true

            return 'Choose a method of contact'
        },
        text(value) {
            if (value?.length > 10) return true

            return 'Add a message with more than 10 characters please'
        },
        checkbox(value) {
            if (value === '1') return true

            return 'Confirm your humanity'
        },
    },
})
const name = useField('name')
const phone = useField('phone')
const email = useField('email')
const select = useField('select')
const text = useField('text')
const checkbox = useField('checkbox')

const items = ref([
    'I want to be called',
    'I want to be emailed',
    'I want to be texted ',
    'I have no preference',
   
])

const submit = handleSubmit(values => {
    alert(JSON.stringify(values, null, 2))
})
</script>

<script>


export default {
    name: 'ContactForm',
    data() {
        return {

            name: '',
            contactMethod: '',
            email: '',
            phone: '',
            message: ''


        }
    },




    methods: {
        async submitForm() {
            try {
                const response = await fetch('https://graces-portfolio.vercel.app/contact', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({
                        name: this.name,
                        message: this.message,
                        email: this.email,
                        phone: this.phone

                    })
                });
                const data = await response.json();
                if (data.success) {
                    alert('Message sent!');
                } else {
                    alert('Error sending message.');
                }
            } catch (error) {
                alert('Failed to send message.');
            }
        }
    }
}

</script>

<style scoped>
.contact-form {
    display: grid;
    grid-template-rows: repeat(5, 1fr);
    font-size: 3rem;
    padding: 15px;
    height: 70vh;
    background-color: rgba(128, 128, 128, 0.7);
    width: 30vw;
    margin: auto;
}

form {
    float: center;
    padding-top: 5%;
}

.v-btn {
    bottom: 12vh;
    left: 70.7vw;
}

input {
    height: 3vh;
    background-color: aliceblue;
    font-size: 1rem;
    padding-left: 20px;
    position: relative;
    top: 50%;
}
.v-container {
    width: 100%;
}
.v-text-field {
    background-color: whitesmoke;
}

.text-input {
    width: 20vw;
}

label {
    /* text-align: center; */
    padding-bottom: -10%;

}

#submit-btn {
    margin-left: 35%;
    padding-top: 3%;
    /* bottom: -30%; */
    position: relative;
}

#name {
    grid-row-start: 1;
    grid-row-start: 2;
}
</style>
