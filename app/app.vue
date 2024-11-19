<script setup lang="ts">
const issues = [
  {
    title: 'Issue 1',
    description: 'Not all toasts are always shown. In this example randomly 1 or 2 are shown instead 2 always.',
  },
  {
    title: 'Issue 2',
    description: 'When updating Nuxt UI from 3.0.0-alpha.7 to 3.0.0-alpha.8 app.vue is not rendered anymore (/ is not found).',
  },
]

const toast = useToast()

function showIssues() {
  issues.forEach((issue) => {
    toast.add({
      title: issue.title,
      description: issue.description,
    })
  })
}
</script>

<template>
  <UApp>
    <div class="flex h-screen justify-center items-center">
      <div class="flex-1 max-w-sm space-y-4">
        <div class="flex justify-center items-center">
          <UIcon name="vscode-icons:file-type-nuxt" class="size-12" />
          <h1 class="text-3xl ml-2">
            Nuxt
          </h1>
        </div>
        <UCard class="text-center">
          Nuxt UI 3 bug reproduction
        </UCard>
        <div class="flex justify-center">
          <UButton @click="showIssues">
            Show issues
          </UButton>
        </div>
      </div>
    </div>
  </UApp>
</template>
