<template>
    <label className="chk">          
        <input
            type="checkbox"
            v-model="isChecked"
          />
          <span className="chk__block"> <CheckMark /> </span>
            <span>{{desc}}</span>

         
    </label>
</template>

<script>
import CheckMark from '../icons/CheckMark.vue';

export default {
    name: 'CheckboxElement',
    props: {
        desc: String
    },
    data() {
        return {
            isChecked: false, // Initialize the checkbox state
        };
    },
    components: { CheckMark }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.chk {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    cursor: pointer;

    span {
        color: #344054;
        font-family: Inter;
        font-size: 14px;
        font-weight: 500;
        line-height: 20px;
    }

    input {
        display: none;
    }

    input:checked ~ .chk__block {
        background: #5429FF;
        border-color: #5429FF;
        svg {
            transform: scale(1);
        }
    }
    &__block {
        border-radius: 4px;
        border: 1px solid #D0D5DD;
        width: 16px;
        height: 16px;
        transition: .2s all ease-in-out ;

        svg {
            fill: white;
            transform: scale(0);
            width: 14px;
            height: 14px;
            transition: .2s all ease-in-out;
        }
    }
}
</style>