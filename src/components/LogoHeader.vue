<template>
    <div class="logo">
        <LogoIcon /> {{ name }}      
    </div>
</template>

<script>
import LogoIcon from './icons/LogoIcon.vue';

export default {
    name: 'LogoVue',
    props: {
        name: String
    },
    components: { LogoIcon }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.logo {
    display: flex;
    align-items: center;
    gap: 12px;
    color: #000;
    font-family: Inter;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.16px;
}
</style>
