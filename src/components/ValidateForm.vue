<template>
  <form class="validate-form-container">
    <!-- 表单插槽 -->
    <slot name="default"></slot>
    <div class="submit-area" @click.prevent="submitForm">
      <!-- 提交按钮 -->
      <slot name="btn">
        <button type="submit" class="btn btn-primary">提交</button>
      </slot>
    </div>
  </form>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  emits: ["form-submit"],
  setup(props, context) {
    const submitForm = () => {
      context.emit("form-submit", true);
    };
    return {
      submitForm
    };
  }
});
</script>
