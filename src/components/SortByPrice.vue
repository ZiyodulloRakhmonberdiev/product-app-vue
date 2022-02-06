<template>
  <select @change="changeOption" class="select">
    <option value="">По умолчанию</option>
    <option value="">От меньшего к большему</option>
    <option value="">От большего к меньшему</option>
  </select>
</template>
<script>
export default {
  name: "SortByPrice",
  props: {
    modelValue: {
      type: String,
    },
    options: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    changeOption(e) {
      this.$emit("update:modelValue", e.target.value);
    },
  },
};
</script>
<style scoped>
.select {
  padding: 10px 16px;
  background: #fffefb;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 4px;
  border: none;
  cursor: pointer;
  color: #b4b4b4;
  outline: none;
  text-align: center;
}
.select option {
  font-size: 12px;
  line-height: 15px;
  color: #b4b4b4;
}
.select option::before {
  margin-right: 5px;
}
@media (max-width: 560px) {
  .select {
    padding: 5px;
  }
}
</style>