<template>
    <div class="userIcon">
        <img src="./iconmonstr-idea-12-24.png" alt="user icon">
    </div>
</template>

<script>
export default {
    name: "UserInfo"
}
</script>

<style scoped>
    .userIcon {
        background: cornflowerblue;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        position: sticky;
        float: right;
        right:2px;
        top: 2px;
    }
</style>