<template>
    <div
      class="text-white flex p-3 my-2 rounded-md"
      :class="current ? 'bg-blue-600' : 'hover:bg-blue-500'"
    >
        <slot name="icon"></slot>
        <span v-if="expanded" class="ml-3">
            {{ label }}
        </span>
    </div>
</template>

<script>
export default {
  props: {
    label: String,
    current: Boolean,
    expanded: Boolean,
  },
  name: 'MenuItem',
  components: {
  },
};
</script>
