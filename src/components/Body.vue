<template>
  <div class="body">
    <AdminPanel />
    <div class="body__content">
      <Header />
      <NewContract />
    </div>
  </div>
</template>

<script>
import AdminPanel from "./Admin_panel";
import Header from "./Header";
import NewContract from "./New_contract";

export default {
  data() {
    return {
      name: "MyBody",
    };
  },
  components: {
    AdminPanel,
    Header,
    NewContract,
  },
};
</script>

<style lang="scss">
.body {
  display: grid;
  grid-template-columns: 303px auto;
  height: 100vh;
  &__content {
    display: grid;
    grid-template-rows: 200px auto;
    width: 100%;
  }
}
</style>