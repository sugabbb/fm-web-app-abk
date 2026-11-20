<template>
  <CDropdown placement="bottom-end" variant="nav-item">
    <CDropdownToggle class="py-0 pe-0" :caret="false" aria-label="Open account menu">
      <CAvatar color="success" text-color="white" size="md">FM</CAvatar>
    </CDropdownToggle>
    <CDropdownMenu class="pt-0">
      <CDropdownHeader
        component="h6"
        class="bg-body-secondary text-body-secondary fw-semibold mb-2 rounded-top"
      >
        Account
      </CDropdownHeader>
      <CDropdownItem component="button" type="button">
        <CIcon icon="cil-user" /> Profile
      </CDropdownItem>
      <CDropdownItem component="button" type="button">
        <CIcon icon="cil-settings" /> Settings
      </CDropdownItem>
      <CDropdownDivider />
      <CDropdownItem component="button" type="button">
        <CIcon icon="cil-lock-locked" /> Logout
      </CDropdownItem>
    </CDropdownMenu>
  </CDropdown>
</template>
