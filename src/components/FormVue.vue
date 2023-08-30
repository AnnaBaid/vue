<template>
  <form className="form">
    <div className="form__title">NFT Access</div>
    <div className="form__desc">Please fill your detail to access your account.</div>
   
    <InputElement title='Email' name='email' type='email' placeholder='Your email' />
    <InputElement title='Password' name='password' type='password' placeholder='Your password' />
    
    <div className="row">
          <CheckboxElement desc='Remember me'/>
            <a href="/">Forgot Password?</a>
        </div>
        <div className="form__btn">
          <ButtonElement className='btn _primary'>Sign in</ButtonElement>
          <ButtonElement className='btn _secondary'> 
            <GoogleIcon />
            Sign in with Google
          </ButtonElement>
        </div>
        <div className="row _center">
          Don’t have an account?
          <a href="/">Sign up</a>
        </div>
  </form>
</template>

<script>
export default {
    components: { GoogleIcon, CheckboxElement, InputElement, ButtonElement }
}
import InputElement from './UI/InputElement.vue';
import GoogleIcon from './icons/GoogleIcon.vue';
import ButtonElement from './UI/ButtonElement.vue';
import CheckboxElement from './UI/CheckboxElement.vue';
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  .form {
    max-width: 360px;
    max-height: 960px;
    margin: auto;
    &__title {
        color: #344054;
        font-family: Inter;
        font-size: 40px;
        font-weight: 700;
        letter-spacing: 0.4px;
        text-transform: capitalize;
        margin-bottom: 8px;
    }
    &__desc {
        color: #667085;
        font-family: Inter;
        font-size: 16px;
        font-weight: 400;
        line-height: 24px;
        margin-bottom: 56px;
    }    
    &__btn {
        display: grid;
        gap: 16px;
        margin-top: 32px;
        margin-bottom: 20px;
    }
   
}

a {
    color: #5429FF;
    font-family: Inter;
    font-size: 14px;
    font-weight: 500;
    line-height: 20px;
    text-decoration: none;
}

</style>
