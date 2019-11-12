<template>
    <header class="header">
        <h1>Scam Trainer</h1>
        <h3>Internet Safety Information</h3>
        <UserInfo />
    </header>
</template>

<script>
import UserInfo from "../UserInfo"

export default {
    name: "Header",
    components: {
        UserInfo
    }
}
</script>

<style scoped>
    .header {
        background: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
        position: fixed;
        width: 100%;
    }
    .header a {
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
    }
    h3 {
        font-style: italic;
        color:silver;
    }
</style>