<template>
  <div class="row">
    <form>
      <div class="col-md-3 offset-md-5 col-lg-12 col-sm-12 col-3 form-group">
        <label for>Quote</label>
        <textarea name rows="3" class="form-control" v-model="quote" style="resize: none"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offest-2 col-md-6 offset-md-5 form-group">
        <button class="btn btn-primary" @click.prevent="createNew">Add Quotes</button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>
<style></style>
