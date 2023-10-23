<template>
  <div>
    <input type="file" @change="uploadImage" />
    <img v-if="imageUrl" :src="imageUrl" alt="Uploaded Image" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      imageUrl: null,
    };
  },
  methods: {
    uploadImage(event) {
      const file = event.target.files[0];
      if (file) {
        this.imageUrl = URL.createObjectURL(file);
        // You can add additional logic here to upload the file to a server if needed.
      }
    },
  },
};
</script>
