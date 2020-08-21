<template>

<li>{{todo}}
  <button @click="$emit('remove', index)">remove</button>
</li>

</template>
<script>
export default {
  name: 'TodoItem',
  props:{
    todo:{
      type: String,
      required:true,
    },
    index:{
      type: Number,
      required: true
    }
  },
}
</script>