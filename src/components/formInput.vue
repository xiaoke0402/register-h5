
<template>
	<div class="form-input" :class="{'form-input--fcous': focus}">
		<input @focus="handlefocus" @blur="focus = false" type="text" :value="value" :disabled="disabled" :placeholder="placeholder" @input="updataValue($event.target.value)">
	</div>
</template>

<script>
export default {
  name: 'form-input',
  data () {
    return {
      focus: false
    }
  },
  props: {
    value: {
      type: [String, Number]
    },
    placeholder: {
      type: [String, Number]
    },
    disabled: {
      type: null
    }
  },
  methods: {
    updataValue(value) {
      this.$emit('input', value)
    },
    handlefocus() {
      this.focus = true
    }
  }
}
</script>

<style>
.form-input {
  box-sizing: border-box;
  width: 100%;
  margin-bottom: 10px;
  border: 1px solid rgb(240, 240, 240);
  border-radius: 4px;
  height: 35px;
  background: #fff;
}
.form-input--fcous {
  border-color: #f86a18;
}
.form-input input {
  width: 100%;
  height: 100%;
  font-size: 14px;
  text-indent: 12px;
  color: rgb(90, 90, 90);
}
.form-input input[disabled]{
  color: rgb(90, 90, 90);
  opacity: 1;
}
input:disabled{
    -webkit-text-fill-color: #000;
    -webkit-opacity: 1;
    color: #000;
}
.form-input input::-webkit-input-placeholder {
  color: rgb(90, 90, 90);
}
</style>
