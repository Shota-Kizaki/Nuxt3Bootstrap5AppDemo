<template>
    <aside class="app-aside">
      <div class="chat-box">
        <div class="message-list">
          <div v-for="message in messages" :key="message.id" class="message">
            {{ message.text }}
          </div>
        </div>
        <div class="input-box">
          <input v-model="newMessage" @keydown.enter="sendMessage" placeholder="Type your message..." />
        </div>
      </div>
    </aside>
</template>
  
<script setup>
import { ref } from 'vue';
  const messages = ref([]);
  const newMessage = ref('');
  
  const sendMessage = () => {
    if (newMessage.trim() === '') return;
    
    messages.value.push({ id: Date.now(), text: newMessage });
    newMessage.value = '';
  
    // OpenAI APIの呼び出しと返信の処理を追加
    // ここでOpenAIのAPIを使用してメッセージの返信を取得する
  };
  </script>