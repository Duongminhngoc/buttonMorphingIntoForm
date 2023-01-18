<template>
  <div id="wrap" class="wrap" :class="{ 'form-open': formOpen }">
    <div class="button" @click="formOpen = true" v-show="!formOpen">
      add product
    </div>
    <div class="form" v-show="formOpen">
      <div class="detail">
        <p class="no-select">Product Title*</p>
        <input
          type="text"
          placeholder="Title"
          v-model="productData.title"
          required="required"
        />
      </div>
      <div class="form-second">
        <div class="detail">
          <p class="no-select">Product Rating*</p>
          <input
            type="number"
            step="0.5"
            min="0"
            max="5"
            placeholder="Rating"
            required="required"
            v-model="productData.rating"
          />
        </div>
        <div class="detail">
          <p class="no-select">Product Price*</p>
          <input
            type="text"
            placeholder="$Price"
            required="required"
            v-model="productData.price"
          />
        </div>
        <div class="detail">
          <p class="no-select">List Price*</p>
          <input
            type="text"
            placeholder="$List Price"
            required="required"
            v-model="productData.list_price"
          />
        </div>
      </div>
      <div class="featured">
        <div @click="productData.is_featured = !productData.is_featured">
          <p class="is-featured no-select">Is Featured</p>
          <i v-show="productData.is_featured" class="far fa-clock"></i>
          <i v-show="!productData.is_featured" class="fas fa-clock"></i>
        </div>
        <p class="note">
          If Is Featured is selected the product will appear in a large card.
        </p>
      </div>
      <div class="description">
        <p class="no-select">Product Description</p>
        <textarea
          name=""
          id=""
          placeholder="Description"
          v-model="productData.description"
        ></textarea>
      </div>
      <div class="add-product">
        <button>add product</button>
      </div>
      <div class="cancel">
        <p @click="cancel()">Cancel</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ButtonForm",
  data() {
    return {
      formOpen: false,
      productData: {
        title: "",
        rating: "",
        price: "",
        list_price: "",
        is_featured: false,
        description: "",
      },
    };
  },
  methods: {
    resetProductData() {
      this.productData = {
        title: "",
        rating: "",
        price: "",
        list_price: "",
        is_featured: false,
        description: "",
      };
    },
    cancel() {
      this.formOpen = false;
      this.resetProductData();
    },
  },
};
</script>

<style lang="scss" scoped>
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  text-transform: uppercase;
  width: 100%;
  height: 100%;
}
.wrap {
  width: 150px;
  height: 150px;
  background-color: blueviolet;
  border-radius: 50%;
  color: #fff;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  &.form-open {
    width: 420px;
    height: 490px;
    background-color: #fafafa;
    border-radius: 5px;

  }
  .form {
    color: #363535;
    padding: 30px;
    animation: opacityAnimation .3s forwards;
  }
}
.detail {
  display: flex;
  flex-direction: column;
  text-align: left;
  margin-bottom: 30px;
}
p {
  font-weight: 600;
  font-size: 15px;
}
.no-select {
  user-select: none;
}
p.note {
  font-weight: 100;
  font-size: small;
  font-style: italic;
  color: #949494;
}
.featured {
  display: flex;
  flex-direction: column;
  text-align: left;
  margin-bottom: 20px;
}
.featured > div {
  margin-bottom: 2px;
}
.is-featured {
  display: inline;
  margin-right: 5px;
}
.form-second {
  display: flex;
  justify-content: space-between;
}
.form-second input {
  width: 100px;
}
.description {
  display: flex;
  flex-direction: column;
  text-align: left;
  margin-bottom: 20px;
}
.description > p {
  margin-bottom: 5px;
}
textarea {
  height: 80px;
  resize: none;
  padding: 5px;
}
input:focus,
textarea:focus {
  border: none;
  outline: 1px #e6b329 solid;
}
.add-product button {
  padding: 15px 50px;
  background-color: #3498db;
  text-transform: uppercase;
  border-radius: 25px;
  border: none;
  color: white;
  font-weight: 700;
  cursor: pointer;
  margin-bottom: 10px;
}
.cancel p {
  display: inline;
  cursor: pointer;
  font-weight: 100;
  font-size: 12px;
}
.cancel p:hover {
  border-bottom: 1px rgb(97, 93, 93) solid;
}
::selection {
  background-color: #f5617a;
  color: #fff;
}
@keyframes opacityAnimation {
  0% {opacity: 0;}
  99% {opacity: 0;}
  100% {opacity: 1;}
}
</style>
