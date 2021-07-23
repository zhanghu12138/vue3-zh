<template>
  <div>
    <validate-form @form-submit="submitForm">
      <div class="mb-3">
        <label for="exampleInputEmail1" class="form-label">Email address</label>
        <validate-input :rules="emailRules" placeholder="请输入正确的邮箱" type="text" v-model="emailVal"></validate-input>
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <validate-input :rules="passwordRules" placeholder="请输入密码" type="text" v-model="passwordVal"></validate-input>
      </div>
      <template #submit>
        <span class="btn btn-danger">submit</span>
      </template>
    </validate-form>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import ValidateForm from '@/components/ValidateForm.vue'
import ValidateInput, { RulesProp } from '@/components/ValidateInput.vue'
import { useRouter } from 'vue-router'
const emailRules: RulesProp = [
  { type: 'required', message: '电子邮箱地址不能为空' },
  { type: 'email', message: '请输入正确的电子邮箱格式' }
]
const passwordRules: RulesProp = [
  { type: 'required', message: '密码不能为空' },
  { type: 'length', length: 6, message: '密码长度不能小于6位' }
]
export default defineComponent({
  name: 'Form',
  components: {
    ValidateInput,
    ValidateForm
  },
  setup () {
    const emailVal = ref('')
    const passwordVal = ref('')
    const router = useRouter()
    const submitForm = (result: boolean) => {
      console.log('1234', result)
      if (result) router.push({ name: 'column', params: { id: 123 } })
    }
    return {
      emailVal,
      passwordVal,
      emailRules,
      passwordRules,
      submitForm
    }
  }
})
</script>
