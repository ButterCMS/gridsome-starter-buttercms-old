<template>
  <Layout>
    <h1>Customer Case Studies</h1>
    <!-- List posts -->
    <div class="customer_case_studies">
      <!-- List posts -->
      <div class="studies">
        <Study
          v-for="edge in $page.studies.edges"
          :key="edge.node.id"
          :study="edge.node"
        />
      </div>
    </div>
  </Layout>
</template>

<page-query>
query {
  studies: allButterCustomerCaseStudy {
    edges {
      node {
        slug
        page_type
        data {
          headline
        	customer_industry
          customer_subindustry
          customer_attributes
          study_date
          customer_logo
        }
      }
    }
  }
}
</page-query>

<script>
import Study from "~/components/CaseStudy.vue";

export default {
  components: {
    Study
  },
  metaInfo: {
    title: "Hello, ButterCMS!"
  }
};
</script>

<style></style>
