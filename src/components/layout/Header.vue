<template>
    <header class="header">
        <h1>Scam Trainer</h1>
        <h2>Internet Safety Information</h2>
        <div class="instruct">Click on a card for more information.</div>
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
        height: 150px;
    }
    .header a {
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
    }
    h2 {
        font-style: italic;
        color:silver;
    }
    
    .instruct {
        color: silver;
    }
</style>