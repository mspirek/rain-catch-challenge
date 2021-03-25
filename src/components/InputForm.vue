<script>
export default {
  name: 'InputForm',
  data () {
    return {
    }
  },
}
</script>

<template>

  <div class="pt-8">
    <div>
      <div class="sm:col-span-3">
        <label for="first_name" class="block text-sm font-medium text-gray-700">
          First name
        </label>
        <div class="mt-1">
          <input type="text" name="first_name" id="first_name" autocomplete="given-name" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md">
        </div>
      </div>
      </div>
  </div>

</template>