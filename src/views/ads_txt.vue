<template>
<div>
<pre>{{ fileContents }}</pre>
</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
data() {
return {
fileContents: ""
};
},
mounted() {
this.getFileContents();
},
methods: {
async getFileContents() {
const response = await fetch("/assets/ads.txt");
const text = await response.text();
this.fileContents = text;
}
}
});
</script>