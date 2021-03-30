<template>
  <div class="body-wrapper">
    <AdminPanel />
    <div class="body-wrapper__content">
      <Header />
      <div class="body-wrapper__contracts">
        <NewContract
          v-for="agreement of agreements"
          :key="agreement.id"
          :agreement="agreement"
        />
      </div>
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
      agreements: [
        {
          id: 1,
          contract: "44-5-10001",
          playground: "ТЭЦ-2",
          playground_address:
            "156009, Костромская обл, Кострома г, Красная Байдарка ул, дом №2",
          isAccept: true,
          value: false,
        },
        {
          id: 2,
          contract: "44-5-10001",
          playground: "ТЭЦ-3",
          playground_address:
            "156009, Костромская обл, Кострома г, Советская ул, дом №120",
          isAccept: false,
          value: false,
        },
        {
          id: 3,
          contract: "67916-м-06405",
          playground: "ВТЭЦ (паровая котельная, водогрейная котельная , ПГУ)",
          playground_address:
            "156009, Костромская обл, Кострома г, Красная Байдарка ул, дом №2",
          isAccept: null,
          value: [
            {
              date: "12.09.2019",
              oldParams: 89573.0,
              newParams: 86573.0,
            },
            {
              date: "13.09.2019",
              oldParams: 5234.98,
              newParams: 12234.7,
            },
            {
              date: "16.09.2019",
              oldParams: 53445.0,
              newParams: 53445.0,
            },
            {
              date: "17.09.2019",
              oldParams: 64758.0,
              newParams: 78758.0,
            },
            {
              date: "18.09.2019",
              oldParams: 64758.0,
              newParams: 78758.0,
            },
            {
              date: "19.09.2019",
              oldParams: 64758.789,
              newParams: 78758.0,
            },
            {
              date: "20.09.2019",
              oldParams: 64758.0,
              newParams: 12758.456,
            },
            {
              date: "21.09.2019",
              oldParams: 64758.0,
              newParams: 89758.0,
            },
            {
              date: "22.09.2019",
              oldParams: 64758.12,
              newParams: 64758.45,
            },
            {
              date: "23.09.2019",
              oldParams: 64758.0,
              newParams: 54758.0,
            },
            {
              date: "24.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "25.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "26.09.2019",
              oldParams: 64758.0,
              newParams: 65758.0,
            },
            {
              date: "27.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "28.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "29.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
          ],
        },
        {
          id: 4,
          contract: "67916-м-06405",
          playground: "ВТЭЦ (паровая котельная, водогрейная котельная , ПГУ)",
          playground_address:
            "156009, Костромская обл, Кострома г, Красная Байдарка ул, дом №2",
          isAccept: null,
          value: [
            {
              date: "12.09.2019",
              oldParams: 2573.0,
              newParams: 2573.0,
            },
            {
              date: "13.09.2019",
              oldParams: 5234.0,
              newParams: 12234.0,
            },
            {
              date: "16.09.2019",
              oldParams: 53445.0,
              newParams: 53445.0,
            },
            {
              date: "17.09.2019",
              oldParams: 64758.0,
              newParams: 40758.0,
            },
            {
              date: "18.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "19.09.2019",
              oldParams: 64758.0,
              newParams: 78758.0,
            },
            {
              date: "20.09.2019",
              oldParams: 64758.0,
              newParams: 12758.0,
            },
            {
              date: "21.09.2019",
              oldParams: 64758.0,
              newParams: 89758.0,
            },
            {
              date: "22.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "23.09.2019",
              oldParams: 64758.0,
              newParams: 68758.0,
            },
            {
              date: "24.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "25.09.2019",
              oldParams: 64758.0,
              newParams: 62758.0,
            },
            {
              date: "26.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "27.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "28.09.2019",
              oldParams: 64758.0,
              newParams: 64758.0,
            },
            {
              date: "29.09.2019",
              oldParams: 64758.0,
              newParams: 61758.0,
            },
          ],
        },
      ],
    };
  },
  components: {
    AdminPanel,
    Header,
    NewContract,
  },
};
</script>

<style lang="scss" scoped>
.body-wrapper {
  display: flex;
  &__content {
    max-width: calc(100vw - 318px);
  }
  &__contracts {
    padding: 20px 30px 40px 20px;
    & > :not(:last-child) {
      margin-bottom: 20px;
    }
  }
}
</style>
