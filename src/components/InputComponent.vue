<template>
  <div class="input">
    <label
      v-if="
        ['success','Autofill','errorFilled', 'filled', 'disabledFilled', 'ReadOnly'].includes(type)
      "
      class="miniText"
      for="input"
      >{{ config.placeholder }}</label
    >
    <input
      name="input"
      type="text"
      :value="value"
      :placeholder="config.placeholder"
      :class="config.type"
      @focus="focus"
      :disabled="disabled"
      :readOnly="readOnly"
      :style="{ background: backgroundColor }"
    />
    <p class="icon" v-html="icon"></p>
    <p class="error_msg" v-if="['errorFilled', 'error'].includes(type)">
      Error - Something
    </p>
    <p>{{description}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    type: {
      type: String,
      default: "default",
    },
    icon: {
      type: String,
      default: "",
    },
    readOnly: {
      type: Boolean,
      default: false,
    },
    description: {
      type: String,
      default: "",
    },
    value: {
      type: String,
      default: "",
    },
    backgroundColor: {
      type: String,
      default: "#fff",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    config: {
      type: Object,
      default: () => {
        return {
          type: "default",
          placeholder: "Your name",
        };
      },
    },
  },
  methods: {
    focus: function () {},
  },
};
</script>

<style scoped>
input {
  border: 0px solid #ccc;
  padding: 16px;
  box-sizing: border-box;
  min-width: 322px;
  min-height: 46px;

  /* Border  */
  border-radius: 4px;

  /* Tipografia */
  font-family: "Roboto";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;

  /*  */
  box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04),
    0px 4px 16px rgba(51, 51, 51, 0.08);
}

.default {
  border: 1px solid #ccc;
}

.miniText {
  position: absolute;
  font-family: "Roboto";
  font-style: normal;
  font-weight: 400;
  font-size: 13px;
  line-height: 20px;
  padding-left: 16px;
  padding-top: 2px;

  /* Color */
  color: rgba(17, 17, 17, 0.48);
}
.error_msg {
  color: rgba(219, 82, 78, 1);
}
.icon {
  position: relative;
  top: -55px;
  left: 290px;
  color: #27AE60;
}
</style>