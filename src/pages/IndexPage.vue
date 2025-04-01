<template>
  <q-page class="flex flex-center column">
    <div class="q-pa-md row justify-center" style="width: 100%">
      <div style="width: 100%; max-width: 400px">
        <q-chat-message
          v-for="message in messages"
          :key="message.id"
          :name="message.name"
          :text="[message.text]"
          :sent="message.sent"
        />
      </div>
    </div>

    <div class="q-pa-md row justify-center" style="width: 100%">
      <div style="width: 100%; max-width: 400px">
        <q-input
          bottom-slots
          v-model="text"
          label="Enter your message"
          outlined
          class="q-mt-md"
        >
          <template v-slot:after>
            <q-btn round dense flat icon="send" />
          </template>
        </q-input>
      </div>
    </div>
  </q-page>
</template>


<script setup>
import { ref } from 'vue';

const text = ref('');

const messages = ref([
  {
    "id": "1",
    "name": "me",
    "text": "How are you?",
    "sent": true,
  },
  {
    "id": "2",
    "name": "Jane",
    "text": "Fine, how are you?",
    "sent": false,
  },
  {
    "id": "3",
    "name": "me",
    "text": "Good, to hear it!",
    "sent": true,
  },
]);
</script>
