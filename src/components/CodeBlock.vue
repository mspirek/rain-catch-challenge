<script>
export default {
  name: 'CodeBlock',
  data () {
    return {
    }
  },
}
</script>

<template>
  <code class="font-mono bg-gray-200 rounded p-4 inline-block">
    <pre>
    <slot />
    </pre>
  </code>
</template>
