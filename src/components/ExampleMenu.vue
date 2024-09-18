<template>
  <div class="dropdown" data-dropdown="true" data-dropdown-trigger="click">
    <button type="button" class="dropdown-toggle btn btn-icon btn-clear btn-light btn-sm">
      <i class="ki-solid ki-dots-horizontal"></i>
    </button>
    <div ref="actionsMenu" class="dropdown-content w-full max-w-56">
      <div class="menu menu-default flex flex-col w-full">
        <div class="menu-item">
          <a class="menu-link dropdown-toggle" href="javascript:void(0)">
            <span class="menu-icon">
              <i class="ki-solid ki-copy"></i>
            </span>
            <span class="menu-title">
              Example menu
            </span>
          </a>
        </div>
        <div class="menu-item">
          <a class="menu-link dropdown-toggle" href="javascript:void(0)">
            <span class="menu-icon">
              <i class="ki-solid ki-copy"></i>
            </span>
            <span class="menu-title">
              Example menu
            </span>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
  import { ref, onMounted, nextTick } from 'vue'
  import { KTReparent } from '../metronic/core/index.ts'

  const actionsMenu = ref(null)
  const actionsMenuInstance = ref(null)

  onMounted(() => {
    nextTick(() => {
      actionsMenuInstance.value = new KTReparent(actionsMenu.value, {
        mode: "append",
        target: "#redbox"
      })
    })
  })
</script>