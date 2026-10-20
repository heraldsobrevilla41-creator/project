<script>
export default {
  props: ['appointArray'],
  data() {
    return {
    }
  },
  methods: {
    xbnt(e) {
      this.$emit('close', e);
    },
    Done(index){
      this.$emit('appointmentIndex', index)
      this.appointArray.splice(index,1);
      alert('Appointment successfully');
      this.appointArray.splice()

    }

  }
}

</script>

<template>
  <div class="fixed inset-0 z-50 flex items-center justify-center bg-black/60 p-4">
    <div
      class="bg-gradient-to-br from-purple-50 to-indigo-50 rounded-xl max-w-2xl w-full p-6 relative shadow-2xl border border-white">

      <button @click="xbnt(false)" class="absolute top-4 right-4 bg-gray-900 text-white w-7 h-7 rounded-full flex items-center justify-center
        text-xs font-bold hover:bg-gray-700">
        ✕
      </button>

      <div class="mb-5">
        <h3 class="text-xl font-serif font-bold text-[#1a1b4b]">My Appointments</h3>
        <p class="text-xs text-gray-600">"Beauty begins the moment you feel confident."</p>
      </div>

      <div v-for="(details, index) in appointArray" :key="index.id" class="space-y-4 border-t mb-2">
        <div>
          <h1 class="text-md font-bold text-gray-700 mb-1 uppercase">Name: {{ details.name }}</h1>
        </div>

        <div class="grid grid-cols-2 gap-10">
          <div>
            <label class="block text-md font-bold text-gray-700 mb-1 uppercase">Appointment Date: {{ details.mydate
            }}</label>

          </div>
          <div>
            <label class="block text-md font-bold text-gray-700 mb-1 uppercase">Time: {{ details.mytime }}</label>

          </div>
        </div>

        <div>
          <h1 class="block text-md font-bold text-gray-700 mb-1 uppercase">Choose Branch: {{ details.myplace }}</h1>

        </div>

        <div>
          <h1 class="block text-md font-bold text-gray-700 mb-1 uppercase">Select Services:{{ details.myservices }}</h1>

        </div>

        <div class="flex items-center justify-end space-x-3 pt-3">
          <button @click="Done(index,false)"
            class="bg-blue-700 hover:bg-blue-500 text-white font-medium text-xs px-6 py-2.5 rounded shadow transition">Done</button>
        </div>
        <!-- <div class="flex items-center justify-end space-x-3 pt-3">
          <button @click="xbnt(false)"
            class="bg-pink-600 hover:bg-pink-700 text-white font-medium text-xs px-6 py-2.5 rounded shadow transition">cancel</button>
        </div> -->


      </div>
    </div>
  </div>
</template>