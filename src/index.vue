<template>
  <div class="ckeditor">
    <div :id="id"></div>
  </div>
</template>
<script>
  let time = new Date().getTime()

  export default {
    name: 'vue-ckeditor',
    props: {
      id: {
        type: String,
        default: () => `editor-${time}`
      },
      config: {
        type: Object,
        default: () => {}
      }
    },
    mounted () {
      if(!window.CKEDITOR){
        console.warn('CKeditor is missing')
      } else {
        window.CKEDITOR.replace(this.id, this.config)
      }
    }

  }
</script>
