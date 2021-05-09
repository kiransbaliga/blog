<template>
  <div class="bg-gray-100 dark:bg-gray-900 text-black dark:text-gray-400 text-center text-sm">
    <div class="container mx-auto py-16">
      <div class="mb-4">
        <p>
          Copyright {{ new Date().getFullYear() }} 
        </p>
      </div>
      <div class="mb-4">
        <ul class="list-reset flex justify-center">
          <li v-for="socialItem in $static.metadata.social" :key="socialItem.name" class="px-4">
            <a :href="socialItem.link" target="_blank" :title="socialItem.name" class="hover:text-blue-500">
              <font-awesome :icon="icon(socialItem.icon)" size="lg"></font-awesome>
            </a>
          </li>
        </ul>
      </div>
      <div class="mb-4">
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    icon(icon) {
      return ['fab', icon]
    }
  }
};
</script>

<static-query>
query {
  metadata {
    siteName

    social {
      name
      icon
      link
    }
  
    footerNavigation {
        name
        link
        external
    }
  }
}
</static-query>