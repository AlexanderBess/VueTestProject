<template>
  <div class="content">
    <div class="content__head head">
      <img
        class="head__img"
        alt="search"
        src="~assets/img/ui/search.svg">
      <input
        class="head__input"
        placeholder="Search"/>
    </div>
    <div class="content__body body">
      <Table
        class="body__table"
        title="Certificates"
        type="Public"
        :table-data="tableData"/>
      <div class="body__additional">
        <div class="body__block">
          <div class="body__title">Filter</div>
          <div class="body__filters">
            <BaseRadioBtn
                label="Public certifications" value="public" v-model="MySelectedValue"/>
            <BaseRadioBtn
                label="Private certifications" value="private" v-model="MySelectedValue"/>
            <BaseRadioBtn
                label="Both" value="both" v-model="MySelectedValue"/>
          </div>
        </div>
        <div class="body__block">
          <div class="body__title">Actions</div>
          <div class="body__actions actions">
            <button
                v-for="(button) in buttons"
                class="actions__button"
                :class="`actions__button_${button.type}`">{{button.name}}</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      MySelectedValue: 'public',
      tableData: [
        "core-t.0",
        "core-t.1",
        "core-t.2",
        "test.test.1",
        "test.test.2",
        "test.test.3",
        "test.test.4",
        "test.test.5",
        "test.test.6",
        "test.test.7"
      ],
      buttons: [
        {
          type: 'active',
          name: 'Create certificate'
        },
        {
          type: 'active',
          name: 'Import certificate'
        },
        {
          type: 'inactive',
          name: 'Export Private certificate to public'
        },
        {
          type: 'inactive',
          name: 'Export certificate to mempool'
        },
        {
          type: 'inactive',
          name: 'Delete certificate'
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.content {
  &__head {
    display: flex;
    align-items: center;
    padding-left: 36px;
    width: 100%;
    height: 60px;
    background: $black1;
    border-radius: 0px 0px 0px 16px;
    box-shadow: inset 1px 1px 0px #524D64;
    filter: drop-shadow(5px 5px 10px rgba(8, 7, 13, 0.42));
  }
  &__body {
    display: flex;
    gap: 40px;
    margin: 24px 40px 24px 21px;
  }
}
.head {
  &__img {
    padding: 0 16px 8px 0;
    border-bottom: 1px solid $black3;
  }
  &__input {
    position: relative;
    padding-bottom: 6px;
    border: none;
    border-bottom: 1px solid $black3;
    outline: none;
    height: 30px;
    min-width: 224px;
    color: #757184;
    font-size: 16px;
    line-height: 24px;
    background: $black1;
  }
  &__input:before {
    position: absolute;
    top: 0px;
    left: -5px;
    content: "~/assets/img/ui/search.svg";
  }
}
.body {
  &__additional {
    margin: 12px 0 0 0;
  }
  &__title {
    margin-bottom: 24px;

    font-weight: 700;
    font-size: 14px;
    line-height: 18px;
  }
  &__filters {
    margin-bottom: 40px;

    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  &__actions {
    display: flex;
    flex-direction: column;
    width: max-content;
    gap: 20px;
  }
}
.actions {
  &__button {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 36px;
    padding: 0 48px 0 48px;
    border-radius: 30px;

    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    color: $white;
    &_active {
      background: linear-gradient(230.15deg, #9580FF 0%, #A361FF 92.48%);
      box-shadow: 2px 2px 7px rgba(11, 10, 13, 0.44), inset 1px 1px 4px #F1E7FF;
    }
    &_inactive {
      background: #B0AEB9;
      box-shadow: 2px 2px 7px rgba(11, 10, 13, 0.44), inset 1px 1px 4px rgba(241, 231, 255, 0.3);
    }
  }
}
@include _991 {
  .content {
    &__body {
      display: flex;
      align-items: center;
      flex-direction: column-reverse;
      margin: 20px;
      gap: 40px;
    }
  }
  .body {
    &__table {
      margin: 0;
    }
    &__additional {
      display: flex;
      justify-content: space-between;
      width: 100%;
      gap: 20px;
    }
    &__actions {
      width: 100%;
    }
  }
}
@include _575 {
  .head {
    &__input {
      min-width: 114px;
    }
  }
  .content {
    &__body {
      gap: 30px;
    }
  }
  .body {
    &__additional {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      width: 100%;
      gap: 30px;
    }
    &__filters {
      margin-bottom: 0;
    }
  }
}
</style>
