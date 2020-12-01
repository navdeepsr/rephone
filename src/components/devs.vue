<template>
  <div class="udevs">
    <div>
      <div class="udvendor">{{ udev.vendor }}</div>
      <div class="uvdev">{{ udev.model }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "devs",
  props: {
    udev: {
      type: Object,
      required: true,
    },
  },
  methods: {
    addUdev(id){
      this.$emit('add-new',id)
    }
  },
};
</script>
<style>
.udevs {
  padding: 10px;
  background-color: white;
  border-radius: 10px;
  box-sizing: border-box;
  cursor: pointer;
  transition: all 0.25 ease;
}
.udevs:hover {
  transform: scale(1.1, 1.1);
}
</style>