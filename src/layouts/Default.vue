<script>
import PageHeader from '@/components/PageHeader';
import PageFooter from '@/components/PageFooter';

export default {
  components: {
    PageHeader,
    PageFooter
  }
}
</script>

<template>
  <div class="layout">
    <page-header />
    <slot/>
    <page-footer />
  </div>
</template>

<static-query>
  query {
    metadata {
      siteName
    }
  }
</static-query>
