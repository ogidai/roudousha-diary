<template>
<div>
    <span class="new-post-button">
        <router-link to="/post" class="">
            <b-icon v-b-toggle.my-sidebar icon="pencil" font-scale="2"></b-icon>
        </router-link>
    </span>
</div>
</template>

<script>
export default {
    name: 'NewPostButton'
}
</script>

<style scoped>
.new-post-button {
    position: fixed;
    bottom: 60px;
    right: 15px;
    background: #d48ce6;
    border-radius: 50%;
    padding: 20px;
}
a {
    color: #fff351;
}
</style>