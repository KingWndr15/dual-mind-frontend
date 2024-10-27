<template>
    <div class="message-form">
        <label for="message">Enter your message:</label>
        <textarea v-model="message" id="message" rows="4" placeholder="Type your message here..."></textarea>

        <label for="style">Choose response style:</label>
        <select v-model="style" id="style">
            <option value="friendly">Friendly</option>
            <option value="formal">Formal</option>
            <option value="informative">Informative</option>
        </select>

        <button @click="sendMessage">Send Message</button>

        <div v-if="response" class="response">
            <h3>AI Response:</h3>
            <p>{{ response }}</p>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    data() {
        return {
            message: "",
            style: "friendly",
            response: null,
        };
    },
    methods: {
        async sendMessage() {
            try {
                const res = await axios.post("http://localhost:3000/api/v1/respond", {
                    message: this.message,
                    style: this.style,
                });
                this.response = res.data.response;
            } catch (error) {
                console.error("Error sending message:", error.message);
                this.response = "Failed to get response from the AI.";
            }
        },
    },
};
</script>

<style>
/* Form and response styling */
.message-form {
    text-align: left;
    margin: 0 auto;
    max-width: 400px;

}

label {
    display: block;
    margin-top: 15px;
    font-weight: bold;
}

textarea {  
    width: 350px !important;
    padding: 10px;
    margin-top: 5px;
    font-size: 16px;
}

select {
    width: 100%;
    padding: 8px;
    margin-top: 5px;
    font-size: 16px;
}

button {
    width: 100%;
    padding: 10px;
    margin-top: 15px;
    background-color: #4CAF50;
    color: white;
    border: none;
    font-size: 16px;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

.response {
    margin-top: 20px;
    background-color: #000;
    padding: 15px;
    border-radius: 8px;
}

.response h3 {
    margin-top: 0;
    color: #fff;
}
</style>