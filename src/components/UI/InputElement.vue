<template>
    <label className="forms">
          <span className="forms__title">{title}</span>
          <div className="forms__input-wraper">
            <input type="inputType" className="forms__input" name="name" value="value" placeholder="placeholder" autocomplete="autocomplete" @input="handleInputChange" />
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
export default {
    name: 'FormVue',
    props: {
        msg: String
    },
    
}
import '@/components/icons/ClearIcon.vue';
import '@/components/icons/EyeIcon.vue';
import '@/components/icons/EyeDefault.vue'

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
    .forms {
    display: block;

    &:not(:last-child) {
        margin-bottom: 20px;
    }

    &__title {
        margin-bottom: 8px;
        color: #344054;
        font-family: Inter;
        font-size: 14px;
        font-weight: 500;
        line-height: 20px;

    }
    &__input-wraper {
        position: relative;
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