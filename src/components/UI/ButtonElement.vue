<template>
    <button className="className">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'className',
    props: {
        msg: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.btn {
    display: inline-flex;
    align-items: center;
    width: 100%;
    border: 0;
    outline: 0;
    cursor: pointer;
    padding: 12px;
    width: 100%;
    justify-content: center;
    gap: 10px;

    &._primary {
        border-radius: 8px;
        background: #5429FF;
        color: #FFF;
        font-family: Inter;
        font-size: 16px;
        font-weight: 500;
        line-height: 20px;
    }

    &._secondary {
        border-radius: 8px;
        border: 1px solid #D0D5DD;
        background: transparent;
        color: #344054;
        font-family: Inter;
        font-size: 16px;
        font-weight: 500;
        line-height: 20px;
    }
}
</style>