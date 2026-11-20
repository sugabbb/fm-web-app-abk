<script setup>
import { onBeforeUnmount, onMounted, ref } from 'vue'
import { useColorModes } from '@coreui/vue'

import AppBreadcrumb from '@/components/AppBreadcrumb.vue'
import AppHeaderDropdownAccnt from '@/components/AppHeaderDropdownAccnt.vue'
import { useSidebarStore } from '@/stores/sidebar.js'

const headerClassNames = ref('mb-4 p-0')
const { colorMode, setColorMode } = useColorModes('farm-management-admin-template-theme')
const sidebar = useSidebarStore()

const updateHeaderShadow = () => {
  headerClassNames.value = document.documentElement.scrollTop > 0 ? 'mb-4 p-0 shadow-sm' : 'mb-4 p-0'
}

onMounted(() => document.addEventListener('scroll', updateHeaderShadow))
onBeforeUnmount(() => document.removeEventListener('scroll', updateHeaderShadow))
</script>

<template>
  <CHeader position="sticky" :class="headerClassNames">
    <CContainer class="border-bottom px-4" fluid>
      <CHeaderToggler
        aria-label="Toggle sidebar"
        style="margin-inline-start: -14px"
        @click="sidebar.toggleVisible()"
      >
        <CIcon icon="cil-menu" size="lg" />
      </CHeaderToggler>
      <CHeaderNav class="ms-auto">
        <CDropdown variant="nav-item" placement="bottom-end">
          <CDropdownToggle :caret="false" aria-label="Select color theme">
            <CIcon v-if="colorMode === 'dark'" icon="cil-moon" size="lg" />
            <CIcon v-else-if="colorMode === 'light'" icon="cil-sun" size="lg" />
            <CIcon v-else icon="cil-contrast" size="lg" />
          </CDropdownToggle>
          <CDropdownMenu>
            <CDropdownItem
              v-for="mode in ['light', 'dark', 'auto']"
              :key="mode"
              :active="colorMode === mode"
              class="d-flex align-items-center text-capitalize"
              component="button"
              type="button"
              @click="setColorMode(mode)"
            >
              <CIcon
                class="me-2"
                :icon="mode === 'light' ? 'cil-sun' : mode === 'dark' ? 'cil-moon' : 'cil-contrast'"
                size="lg"
              />
              {{ mode }}
            </CDropdownItem>
          </CDropdownMenu>
        </CDropdown>
        <li class="nav-item py-1">
          <div class="vr h-100 mx-2 text-body text-opacity-75"></div>
        </li>
        <AppHeaderDropdownAccnt />
      </CHeaderNav>
    </CContainer>
    <CContainer class="px-4" fluid>
      <AppBreadcrumb />
    </CContainer>
  </CHeader>
</template>
