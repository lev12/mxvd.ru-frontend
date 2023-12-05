<template>
<div class="input-contact-container">
  <input type="tel" class="input-contact" :placeholder="placeholder">
  <div class="contact-type" @click="contactSwitchView">
    <Icon :name="contactIcon" class="contact-type-icon"/>
    <Icon :name="!showTypeContactList ? 'triangle-down' : 'triangle-up'" class="contact-type-triangle"/>
  </div>
  <div class="contact-type-list" v-show="showTypeContactList">
    <Icon v-for="item in typeContact" v-if="item.id !== typeContactSelect"
         :name="item.icon" class="contact-type-list_item" @click="typeContactSelect = item.id"/>
  </div>
</div>
</template>

<style lang="scss">
.input-contact-container {
  width: 100%;
  position: relative;

  .input-contact {
    @include text-font;
    border-radius: 10px;
    padding: 6px 8px;
    border: 1px solid $text-black-lighter-color;

    width: 100%;

    position: relative;
    z-index: 10;
  }

  .contact-type {
    display: flex;
    flex-direction: row;
    align-items: center;

    position:absolute;
    right: 8px;
    top: 0px;
    bottom: 0px;
    z-index: 10;

    filter: invert(20%);
  }

  .contact-type-icon {
    height: 28px;
    width: 28px;
  }

  .contact-type-triangle {
    height: 14px;
    width: 14px;
    margin-left: 8px;
    margin-bottom: 8px;
  }

  .contact-type-list{
    display: flex;
    flex-direction: column;
    align-items: center;

    position:absolute;
    right: 0px;
    top: 20px;

    background: $primary-color;
    border: 1px solid $text-black-lighter-color;
    border-radius: 10px;
    padding-top: 20px;

    width: 64px;

    z-index: 9;
  }

  .contact-type-list_item {
    height: 28px;
    width: 28px;
    filter: invert(20%);
    margin-right: 20px;
    margin-bottom: 6px;
    margin-left: 6px;
  }
}
</style>

<script>
export default {
  data: () => { return {
      showTypeContactList: false,
      typeContactSelect: "e-mail",
      typeContact: [
        {
          id: "tel",
          icon: "phone",
          name: "телефон"
        },
        {
          id: "e-mail",
          icon: "e-mail",
          name: "e-mail"
        },
        {
          id: "telegram",
          icon: "telegram",
          name: "telegram"
        },
        {
          id: "whatsapp",
          icon: "whatsapp",
          name: "whatsapp"
        },
        {
          id: "viber",
          icon: "viber",
          name: "viber"
        }
      ]
    }
  },
  computed: {
    placeholder() {
      return "Введите " + this.contactName;
    },
    contactIcon() {
      for (let i = 0; i < this.typeContact.length; i++) {
        const element = this.typeContact[i];
        if (element.id === this.typeContactSelect) return element.icon;
      }
      return "";
    },
    contactName() {
      for (let i = 0; i < this.typeContact.length; i++) {
        const element = this.typeContact[i];
        if (element.id === this.typeContactSelect) return element.name;
      }
      return "";
    }
  },
  methods: {
    contactSwitchView()
    {
      this.showTypeContactList = !this.showTypeContactList;
    }
  },

}
</script>
