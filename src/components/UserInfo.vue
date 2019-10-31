<template>
    <div class="userIcon">
        <img src="../assets/iconmonstr-user-1-32.png" alt="user icon">
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
        float: right;
        right: 20px;
        top: 20px;
        position: absolute;
    }
</style>