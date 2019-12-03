<template>
    <div id="userIcon" :class="{ 'active' : isIconActive }" @click.prevent="toggle">
        <slot>
            <button type="button" class="userIcon" title="User Information">
                <img src="../assets/iconmonstr-user-1-32.png" alt="user icon">
            </button>
        </slot>
        <div>User Info</div>
    </div>
</template>

<script>
import { store, mutations } from '@/store.js'

export default {
    name: "UserInfo",
    computed: {
        isIconActive() {
            return store.isNavOpen
        }
    },
    methods: {
        toggle() {
            mutations.toggleNav()
        }
    }
}
</script>

<style scoped>
    .userIcon {
        background: #fff;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
    }

    .hidden {
        visibility: hidden;
    }

    button {
        cursor: pointer;
    }

    /* remove blue outline */
    button:focus {
        outline: 0;
    }

    #userIcon {
        float: right;
        right: 30px;
        top: 45px;
        position: absolute;
    }
</style>