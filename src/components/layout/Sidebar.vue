<template>
    <div class="sidebar">
        <div class="sidebar-backdrop" @click="closeSidebarPanel" v-if="isPanelOpen"></div>
        <transition name="slide">
            <div v-if="isPanelOpen" class="sidebar-panel">
                <div>
                    <button type="button" class="back-button" title="Close User Information" @click="closeSidebarPanel">
                        <img class="back-arrow" src="@/assets/iconmonstr-arrow-2-240.png" alt="right arrow icon">
                    </button>
                </div>
                <slot>User Information</slot>
            </div>
        </transition>
    </div>
</template>

<script>
import { store, mutations } from '@/store.js'

export default {
    computed: {
            isPanelOpen() {
                return store.isNavOpen
            }
        },
    methods: {
        closeSidebarPanel: mutations.toggleNav
    }
}
</script>

<style>
    .slide-enter-active,
    .slide-leave-active
    {
        transition: transform 0.4s ease;
    }

    .slide-enter,
    .slide-leave-to {
        transform: translateX(100%);
        transition: all 150ms ease-in 0s
    }

    .sidebar-backdrop {
        background-color: rgba(0,0,0,.5);
        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        right: 0;
        cursor: pointer;
    }

    .sidebar-panel {
        overflow-y: auto;
        background-color: #ACB9E8;
        position: fixed;
        right: 0;
        top: 0;
        height: 100vh;
        z-index: 999;
        padding: 4rem 40px 2rem 40px;
        width: 300px;
    }

    .back-button {
        cursor: pointer;
        display: contents;
    }

    .back-arrow {
        height: 36px;
        width: 36px;
        top: 10px;
        left: 10px;
        position: absolute;
    }
</style>