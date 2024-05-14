<template>
  <div>
    <Header />
    <Tools />
    <div >
      <DataTable  />
      <Footer />
    </div>
  </div>
</template>

<script>
import DataTable from '../components/dataTable.vue';
import Footer from '../components/footer.vue';
import Header from '../components/header.vue';
import Tools from '../components/tools.vue';


export default {
  name: 'IndexPage',
  components: {
    Header,
    Tools,
    DataTable,
    Footer
  }
}
</script>
