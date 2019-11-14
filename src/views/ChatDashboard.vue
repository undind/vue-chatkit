<template>
  <div class="chat-dashboard">
    <ChatNavBar />
    <b-container fluid class="ld-over" v-bind:class="{ running: loading }">
      <div class="ld ld-ring ld-spin"></div>
      <b-row>
        <b-col cols="2">
          <RoomList />
        </b-col>

        <b-col cols="8">
          <b-row>
            <b-col id="chat-content">
              <MessageList />
            </b-col>
          </b-row>
          <b-row>
            <b-col>
              <MessageForm />
            </b-col>
          </b-row>
        </b-col>

        <b-col cols="2">
          <UserList />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  components: {
    ChatNavBar: () => import('@/components/ChatNavBar.vue'),
    MessageForm: () => import('@/components/MessageForm.vue'),
    MessageList: () => import('@/components/MessageList.vue'),
    RoomList: () => import('@/components/RoomList.vue'),
    UserList: () => import('@/components/UserList.vue'),
  },
  computed: {
    ...mapState(['loading'])
  },
}
</script>