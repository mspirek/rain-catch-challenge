<script>
export default {
  metaInfo: {
    title: 'Home'
  },

  data: () => ({
    heightArr: [0, 1, 0, 2, 1, 0, 1, 3, 2, 1, 2, 1],
    number: 0,
  }),

  methods: {
    clearArray() {
      this.heightArr = []
    },
    addToArray() {
      this.heightArr.push(Number(this.number))
      this.number = 0;
    }
  },
  computed: {
    rainCatchAmount() {
      let leftMax = -1,
          rightMax = -1,
          left = 0,
          right = this.heightArr.length - 1,
          water = 0;

      while (left <= right) {
        leftMax = this.heightArr[left] > leftMax ? this.heightArr[left] : leftMax
        rightMax = this.heightArr[right] > rightMax? this.heightArr[right] : rightMax

        if (leftMax > rightMax) {
          water += rightMax - this.heightArr[right]
          right--
        }
        else {
          water += leftMax - this.heightArr[left]
          left++
        }
      }

      return water
    }
  }
}

</script>


<template>
  <Layout>
    <div class="container mx-auto py-8 text-center">
      <div class="pb-12 text-2xl">
        <span class="font-bold">Water Caught: {{rainCatchAmount}}</span>
      </div>

      <div class="flex justify-center pb-6">
        <div v-for="(blocks, idx) in heightArr" :key="idx" class="self-end text-center">
          <div v-if="blocks === 0" class="h-20 w-20 bg-white" />
          <div v-for="(block, idx) in blocks" class="flex flex-col" :key="idx">
            <div class="h-20 w-20 bg-black" />
          </div>
          <div class="pt-4">idx: {{ idx }} <br> height: {{ blocks}}</div>
        </div>
      </div>

      <div class="pb-6">
        <span class="font-bold">Height Array:</span> {{ heightArr }}
      </div>

      <div class="">
        <div class="pb-2">
          <label class="block font-bold pb-1">Number To Add</label>
          <input type="number" min="0" v-model="number" class="border border-gray-500 rounded py-1 px-2">
        </div>
        <div class="flex py-2 justify-center">
          <button class="bg-blue-500 rounded p-2 text-white mr-2" @click="addToArray">Add to Array</button>
          <button class="bg-blue-400 rounded p-2 text-white" @click="clearArray">Clear Array</button>
        </div>
      </div>

    </div>

  </Layout>
</template>