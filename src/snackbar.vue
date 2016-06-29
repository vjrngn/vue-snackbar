<template>
  <div class="mdl-js-snackbar mdl-snackbar">
    <div class="mdl-snackbar__text"></div>
    <button class="mdl-snackbar__action" type="button"></button>
  </div>
</template>

<script>
  export default {
      props: {
        message: {
          required: true
        },
        actionText: {
          required: true
        },
        actionHandler: {
          required: true
        },
        timeout: {
          required: false,
          default: 2000
        },
        displayWhen: {
          type: 'String'
        }
      },

      ready: function() {
        this.$on(this.displayWhen, function(snackbarData) {
          this.show(snackbarData);
        })
      },

      data: function() {
        return {
          snackbarData: {
            message: this.message,
            timeout: this.timeout,
            actionHandler: this.actionHandler,
            actionText: this.actionText
          }
        };
      },

      methods: {
        show: function(data) {
          if (data === undefined) {
            data = this.snackbarData;
          }

          this.$el.MaterialSnackbar.showSnackbar(data);
        }
      }
  }
</script>
