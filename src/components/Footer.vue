<template>
  <div class="absolute bottom-0 flex justify-between w-full px-8 py-2 text-gray-900 bg-gray-500">
    <h3>Copyright &copy; {{ new Date().getFullYear() }}</h3> 
    <div class="flex">
      <a href="mailto:macedo@developintech.com" class="mr-2">
        Arcadio Macedo
      </a>
      <a href="https://twitter.com/ArcadioMacedo" class="mx-2">
        <img src="../assets/icons/twitter.png" alt="Twitter icon" class="w-4 h-4 mt-1" >
      </a>
      <a href="https://github.com/makmacedo" class="mx-2">
        <img src="../assets/icons/github.png" alt="GitHub icon" class="w-4 h-4 mt-1" >
      </a>
      <a href="https://www.linkedin.com/in/arcadio-macedo/" class="mx-2">
        <img src="../assets/icons/linkedin.png" alt="Linkedin icon" class="w-4 h-4 mt-1" >
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>
