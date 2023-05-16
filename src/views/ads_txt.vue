<template>
  <div>
    <pre>{{ fileContents }}</pre>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      fileContents: ""
    };
  },
  mounted() {
    this.getFileContents();
  },
  methods: {
    getFileContents() {
      fetch("/assets/ads.txt")
        .then(response => response.text())
        .then(text => {
          this.fileContents = text;
        });
    }
  }
};
</script>
