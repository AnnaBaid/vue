<template>
    <label className="forms">
          <span className="forms__title">{{title}}</span>
          <div className="forms__input-wraper">
            <input :type="inputType" className="forms__input" :name="name" :value="value" :placeholder="placeholder" autocomplete="autocomplete" @input="handleInputChange" />
            <div className="forms__input-svg">
                <span v-if="type !== 'password'" @click="handleClearIcon" >
                    <ClearIcon />
                </span>
                <span v-if="type === 'password'" @click="handleTogglePassword" >
                    <template v-if="showPassword">
                        <EyeIcon />
                    </template>
                    <template v-else>
                        <EyeDefault />
                    </template>                        
                </span>                     
            </div>
          </div>
    </label>
</template>

<script>
import { ref } from 'vue';

import ClearIcon from '../icons/ClearIcon.vue';
import EyeIcon from '../icons/EyeIcon.vue';
import EyeDefault from '../icons/EyeDefault.vue'; 

export default {
    name: 'InputElement',
    props: {
        title: String,
        type: String,
        name: String,
        placeholder: String
    },
    components: {
        ClearIcon,
        EyeIcon,
        EyeDefault
    },
    setup(props) {
        const value = ref("");
        const showPassword = ref(false);
        const handleInputChange = (e) => (
            value.value = e.target.value
        );

        const handleClearIcon = () => (
            value.value = ""
        );

        const handleTogglePassword = () => {
            showPassword.value = !showPassword.value
        };

        const inputType = (() => showPassword.value ? "text" : props.type);

        return {
            value,
            showPassword,
            handleClearIcon,
            handleInputChange,
            handleTogglePassword,
            inputType,
            autocomplete: "off"
        };

    }
};


</script>

<style lang="scss">
    .forms {
    display: block;
  

    &__title {
        display: flex;
        margin-bottom: 8px;
        color: #344054;
        font-family: Inter;
        font-size: 14px;
        font-weight: 500;
        line-height: 20px;

    }
    &__input-wraper {
        position: relative;
        margin-bottom: 20px;
    }

    &__input-svg {
        cursor: pointer;
        position: absolute;
        right: 14px;
        top: 50%;
        transform: translateY(-50%);
        span {
            display: flex;
        }
    }
    &__input {
        height: 44px;
        width: 100%;
        display: block;
        padding: 10px 14px;
        border-radius: 8px;
        border: 1px solid #D0D5DD;
        background: transparent;
    }

}
</style>