<template>
    <v-card>
        <v-card-title>New chat</v-card-title>
        <v-card-text>
            <v-list>
                <v-list-item v-for="message in messages" :key="message.id">
                <v-list-item-content>
                    <v-list-item-title>{{ message.text }}</v-list-item-title>
                    <div class="chat-date">
                        <small>{{ new Date(message.id) }}</small>
                    </div>
                </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-card-text>
        <v-card-actions>
            <v-text-field v-model="inputText" label="Message" outlined hide-details></v-text-field>
            <v-btn class="send-btn" color="primary" @click="sendMessage">Send</v-btn>
        </v-card-actions>
    </v-card>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

@Component
export default class ChatComponent extends Vue {
  private inputText: string = '';
  private messages: { id: number; text: string }[] = [];

  private sendMessage(): void {
    if (this.inputText.trim() !== '') {
      const uniqueId = Date.now();
      this.messages.push({ id: uniqueId, text: this.inputText });
      this.inputText = '';
    }
  }
}
</script>

<style scoped>
.v-card {
    height: 100%;
}

.v-card__title
, .v-card__actions {
    height: 5rem;
}

.v-card__text {
    height: calc(100% - 10rem);
}

.v-list {
    height: 100%;
    overflow-y: auto;
}

.v-list-item__content {
    padding: 16px;
    margin: 2px;
    color: rgb(133, 133, 133);
    background-color: #f3f3f3;
}

.v-list-item__title {
  white-space: normal; /* 메시지 길이가 일정 길이를 초과하면 자동으로 줄바꿈 */
}

.chat-date {
    margin-top: 1rem;
    text-align: end;
}

.send-btn {
    margin-left: 1rem;
}
</style>
