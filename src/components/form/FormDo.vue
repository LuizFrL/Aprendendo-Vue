<template>
  <div class="mx-auto col-5">
    <b-form-tags v-model="value" class="mb-2" placeholder="Tasks para fazer..."></b-form-tags>
    <p>Value: {{ value }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: []
    };
  }
};
</script>