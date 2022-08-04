<script lang="ts">
export default {
  name: "ReImageVerify"
};
</script>

<script setup lang="ts">
import { watch } from "vue";
import { useImageVerify } from "./hooks";

interface Props {
  code?: string;
}

interface Emits {
  (e: "update:code", code: string): void;
}

const props = withDefaults(defineProps<Props>(), {
  code: ""
});

const emit = defineEmits<Emits>();

const { domRef, imgCode, setImgCode, getImgCode } = useImageVerify();

watch(
  () => props.code,
  newValue => {
    setImgCode(newValue);
  }
);
watch(imgCode, newValue => {
  emit("update:code", newValue);
});

defineExpose({ getImgCode });
</script>

<template>
  <canvas
    ref="domRef"
    class="cursor-pointer"
    height="40"
    width="120"
    @click="getImgCode"
  />
</template>
