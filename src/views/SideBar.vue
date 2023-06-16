<template>
    <div class="icon-bar">
        <div class="new-chat">
            <a><router-link to="/new/chat">
                <v-icon>mdi-plus</v-icon>&nbsp;&nbsp;&nbsp;New chat
            </router-link></a>
        </div>
        <a><router-link to="/chat">
            <v-icon>mdi-message</v-icon>&nbsp;&nbsp;&nbsp;채팅1
        </router-link></a>
        <a><router-link to="/chat">
            <v-icon>mdi-message</v-icon>&nbsp;&nbsp;&nbsp;채팅2
        </router-link></a>
        <div class="user-info">
            <a><router-link to="/logout">
                <v-icon>mdi-logout</v-icon>&nbsp;&nbsp;&nbsp;유저1
            </router-link></a>
        </div>
    </div>
</template>

<style>
.icon-bar {
    height: 100%;
    width: 15rem;
    background-color: #e4e4e4;
    position: fixed; /* Fixed Sidebar (stay in place on scroll) */
    /*z-index: 1;*/ /* Stay on top */
    top: 0; /* Stay at the top */
    left: 0;
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 0;
}
.icon-bar__dark {
    height: 100%;
    width: 15rem;
    background-color: #777777;
    position: fixed; /* Fixed Sidebar (stay in place on scroll) */
    /*z-index: 1;*/ /* Stay on top */
    top: 0; /* Stay at the top */
    left: 0;
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 0;
}

.new-chat {
    border-bottom: solid 1px #afafaf;
}

.icon-bar a router-link
, .icon-bar__dark a router-link {
    display: block;
    height: 4rem;
    padding: 1rem;
    padding-left: 1.5rem;
    transition: all 0.3s ease;
    color: black;
}

.icon-bar a router-link:hover
, .icon-bar__dark a router-link:hover {
    background-color: #858585;
}

.user-info {
    border-top: solid 1px #afafaf;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 15rem;
}
</style>