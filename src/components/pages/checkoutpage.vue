<template>
  <div
    :class="isCard ? '' : 'lg:h-screen'"
    class="container mx-auto p-6 grid grid-cols-1 row-gap-12 lg:grid-cols-10 lg:col-gap-10 lg:pt-12"
  >
    <Payment
      @handle-card="handleCard"
      @change-parent="handleAlert"
      :total="total"
    />
    <Summary :items="items" />
    <Alert
      :visible="alertVisible"
      position="top-right"
      color="success"
      title="Success"
      description="Your payment has been successfully processed."
    />
  </div>
</template>
<script>
import Payment from "../Payment";
import Summary from "../Summary";
import Alert from "../Alert";

export default {
  name: "CheckoutPage",
  components: {
    Payment,
    Summary,
    Alert,
  },
  data() {
    return {
      items: [
        {
          title: "Title 1",
          description: "lorem impsu liwe",
          price: 550,
        },
        {
          title: "Title 2",
          description: "lorem impsu liwe",
          price: 250,
        },
        {
          title: "Title 3",
          description: "lorem impsu liwe",
          price: 150,
        },
      ],
      alertVisible: false,
      total: 0,
      isCard: false,
    };
  },
  mounted() {
    this.getTotal(this.items);
  },
  methods: {
    getTotal(items) {
      items.forEach((element) => {
        this.total += element.price;
      });
    },
    handleAlert() {
      this.alertVisible = true;
      setTimeout(() => {
        this.alertVisible = false;
      }, 100);
    },
    handleCard() {
      this.isCard = true;
    },
  },
};
</script>