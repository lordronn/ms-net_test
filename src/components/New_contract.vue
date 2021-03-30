<template>
  <div class="contract">
    <div class="contract__wrapper">
      <div class="contract__num">
        <p class="contract__name">
          Договор
        </p>
        <span>{{ agreement.contract }}</span>
      </div>
      <div class="contract__playground">
        <p class="contract__name">
          Площадка
        </p>
        <span>{{ agreement.playground }}</span>
      </div>
      <div class="contract__address">
        <p class="contract__name">
          Адрес площадки
        </p>
        <span>
          {{ agreement.playground_address }}
        </span>
      </div>
      <div
        v-if="agreement.isAccept !== null"
        :class="[
          agreement.isAccept
            ? 'contract__finish-info_accept'
            : 'contract__finish-info_reject',
          'contract__finish-info',
        ]"
      >
        <p
          class="contract__name"
          v-if="true"
        >
          Изменения приняты
        </p>
        <p
          class="contract__name"
          v-if="false"
        >
          Изменения отклонены
        </p>
      </div>
    </div>
    <div
      v-if="agreement.value"
      class="contract__value"
    >
      <div class="contract__table">
        <div
          v-for="data of agreement.value"
          :key="data.date"
          class="colomn"
        >
          <div class="colomn__header">
            <span>
              {{ data.date }}
            </span>
          </div>
          <div class="colomn__old-params">
            <span>
              {{ typecast(data.oldParams) }}
            </span>
          </div>
          <div class="colomn__new-params">
            <span
              :class="[
                numCheck(data.oldParams, data.newParams) === 'higher'
                  ? 'higher-price'
                  : '',
                numCheck(data.oldParams, data.newParams) === 'decrease'
                  ? 'decrease-price'
                  : '',
              ]"
            >
              {{ typecast(data.newParams) }}
            </span>
          </div>
        </div>
      </div>

      <div class="contract__total">
        <div class="wrapper">
          <p>Прошлый объем:</p>
          <p>
            {{ typecast(oldParams) }}
          </p>
        </div>
        <div class="wrapper">
          <p>Новый объем:</p>
          <p
            :class="[
              numCheck(oldParams, newParams) === 'higher' ? 'higher-price' : '',
              numCheck(oldParams, newParams) === 'decrease'
                ? 'decrease-price'
                : '',
            ]"
          >
            {{ typecast(newParams) }}
          </p>
        </div>
      </div>
      <div>
        <button class="contract__take">
          Принять изменения
        </button>
        <button class="contract__ignore">
          Отклонить изменения
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: { agreement: Object },
  data() {
    return {
      name: "NewContract",
      oldParams: 0,
      newParams: 0,
    };
  },
  methods: {
    digitization(string) {
      return parseFloat(string.replace(" ", ""));
    },
    numCheck(numOld, numNew) {
      if (numOld < numNew) {
        return "higher";
      } else if (numOld > numNew) {
        return "decrease";
      } else return null;
    },
    checkingResults() {
      let oldPar = 0;
      let newPar = 0;
      if (this.agreement.value) {
        this.agreement.value?.forEach((element) => {
          (oldPar += element.oldParams), (newPar += element.newParams);
        });
      }

      this.oldParams = oldPar;
      this.newParams = newPar;
    },
    typecast(num) {
      return num.toString().replace(/(\d)(?=(\d\d\d)+(?!\d))/g, "$1 ");
    },
  },
  mounted() {
    this.checkingResults();
  },

  components: {},
};
</script>

<style lang="scss" scoped>
.contract {
  padding: 20px;
  box-sizing: border-box;
  min-height: 87px;
  box-shadow: 0px 4px 16px rgba(70, 70, 79, 0.2);
  border-radius: 4px;

  &__wrapper {
    display: flex;
  }
  &__num,
  &__playground {
    margin-right: 40px;
  }
  &__name {
    color: #838588;
    font-weight: 500;
    font-size: 11px;
    margin: 0;
    margin-bottom: 5px;
  }
  &__finish-info {
    display: flex;
    margin: auto 0;
    margin-left: auto;
    & > p {
      width: 71px;
      margin: 0;
    }
    &_accept {
      &:before {
        content: url("data:image/svg+xml,%3Csvg width='31' height='30' viewBox='0 0 31 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Crect x='0.5' width='30' height='30' rx='15' fill='%231473FA'/%3E%3Cg clip-path='url(%23clip0)'%3E%3Cpath d='M7.30078 13.5L14.2008 20.4L25.7008 8.9' stroke='white'/%3E%3C/g%3E%3Cdefs%3E%3CclipPath id='clip0'%3E%3Crect width='19' height='20' fill='white' transform='translate(6.5 5)'/%3E%3C/clipPath%3E%3C/defs%3E%3C/svg%3E%0A");
        margin-right: 10px;
        width: 30px;
        height: 30px;
      }
    }
    &_reject {
      &:before {
        content: url("data:image/svg+xml,%3Csvg width='31' height='30' viewBox='0 0 31 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Crect x='0.5' width='30' height='30' rx='15' fill='%23FF144D'/%3E%3Cpath d='M8.5 7.10522L23.5 22.8947M8.5 22.8947L23.5 7.10522' stroke='white'/%3E%3C/svg%3E%0A");
        margin-right: 10px;
        width: 30px;
        height: 30px;
      }
    }
  }

  &__value {
    margin-top: 20px;
  }

  &__table {
    display: flex;
    max-height: 220px;
    overflow-x: auto;
    margin-bottom: 30px;
    &::-webkit-scrollbar {
      width: 1220px;
      height: 9px;
      background: #f4f4f4;
      border-radius: 10px;
    }
    &::-webkit-scrollbar-thumb {
      background: #1473fa;
      border-radius: 10px;
      height: 5px;
    }

    .colomn {
      min-width: 110px;
      min-height: 150px;
      display: grid;
      grid-template-rows: repeat(3, 62px);
      &__higher-price {
        color: #00c4a8;
      }

      &__header {
        background: #464851;
        color: #ffffff;
      }
      &__old-params,
      &__new-params {
        background-color: #f2fbff;
      }
      &__header,
      &__old-params,
      &__new-params {
        display: flex;
        & > span {
          margin: auto;
        }
      }
    }
  }

  &__total {
    display: flex;
    flex-direction: column;
    .wrapper {
      display: flex;
      justify-content: space-between;
      max-width: 230px;
      font-size: 13px;
      & > p {
        margin-top: 0;
      }
    }
  }
  &__take,
  &__ignore {
    padding: 16px 31px;
    border: 1px solid #1473fa;
    border-radius: 4px;
    color: #1473fa;
    background: none;
    min-width: 225px;
    outline: none;
    cursor: pointer;
    &:hover {
      background-color: #e5e5e5;
    }
  }
  &__take {
    &:before {
      content: url("data:image/svg+xml,%3Csvg width='14' height='10' viewBox='0 0 14 10' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 4L5.6669 8.6669L13.4451 0.88873' stroke='%231473FA'/%3E%3C/svg%3E%0A");
      margin-right: 10px;
    }
    margin-right: 20px;
  }
  &__ignore {
    &:before {
      content: url("data:image/svg+xml,%3Csvg width='10' height='10' viewBox='0 0 12 12' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1 1L11 11M1 11L11 0.999998' stroke='%231473FA'/%3E%3C/svg%3E%0A");
      margin-right: 10px;
    }
  }
  & span {
    font-size: 14px;
  }
}
.higher-price {
  color: #00c4a8;
}
.decrease-price {
  color: #ff6969;
}
</style>
