<template>
  <div>
    <label :for="name">{{ label }}</label>
    <input
      v-if="type !== 'textarea'"
      :id="name"
      :name="name"
      :type="type"
      v-model="inputValue"
    />
    <textarea
      v-else
      :id="name"
      :name="name"
      v-model="inputValue"
    ></textarea>
    <span v-if="error" class="error">{{ error }}</span>
  </div>
</template>

<script>
export default {
  name: 'FormInput',
  props: {
    label: String,
    name: String,
    type: {
      type: String,
      default: 'text',
    },
    modelValue: [String, Number],
    error: String,
  },
  computed: {
    inputValue: {
      get() {
        return this.modelValue;
      },
      set(value) {
        this.$emit('update:modelValue', value);
      },
    },
  },
};
</script>

<style>
.error {
  color: red;
  font-size: 12px;
}
</style>
