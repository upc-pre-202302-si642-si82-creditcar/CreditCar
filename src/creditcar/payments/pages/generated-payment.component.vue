<script>
import ButtonPrimary from "@/creditcar/shared/components/button-primary.component.vue";
import {PaymentApiService} from "@/creditcar/payments/services/payment-api.service";

export default {
  name: "generated-payment",
  components: {ButtonPrimary},
  data() {
    return {
      paymentApi: null,
      payment: null,
    }
  },
  created() {
    this.paymentApi = new PaymentApiService();
    this.paymentApi.getAll().then((response) => {
      this.payment = response.data;
    });
  },
}

</script>

<template>
  <div class="mb-6">
    <div class="flex items-center h-fit mb-20 bg-gray-200">
      <div class="w-full md:w-1/2 text-center my-20 mx-5">
        <p class="text-6xl font-bold mb-4">Plan de pagos resultante</p>
      </div>
    </div>
  </div>

  <div class="max-w-4xl mx-auto">
    <pv-card class="card mt-0 md:mx-50 md:px-5">
      <template #content>
        <div class="px-5">
          <h2 class="text-center font-bold">Información del vehículo</h2>
          <p class="mb-3"><span class="text-[--red] font-bold">Marca</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Modelo</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Precio</span> {{}}</p>

          <hr class="division mb-3">

          <h2 class="text-center font-bold">Información ingresada</h2>
          <p class="mb-3"><span class="text-[--red] font-bold">Tipo de moneda</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Tasa de interés</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Frecuencia de pago</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Plazo de pago</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">Cuota final</span> {{}}</p>

          <hr class="division mb-3">

          <h2 class="text-center font-bold">Resultados</h2>
          <p class="mb-3"><span class="text-[--red] font-bold">COK</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">TEA</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">TCEA</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">VAN</span> {{}}</p>
          <p class="mb-3"><span class="text-[--red] font-bold">TIR</span> {{}}</p>

          <div class="pt-5">
            <pv-data-table
                class="overflow-hidden mb-4"
                :value="[payment]"
                :paginator="true"
                :rows="10"
                paginatorTemplate="FirstPageLink PrevPageLink PageLinks NextPageLink LastPageLink CurrentPageReport RowsPerPageDropdown">
              <pv-column field="number" header="Nº"></pv-column>
              <pv-column field="TEA" header="TEA"></pv-column>
              <pv-column field="TEP" header="TEP"></pv-column>
              <pv-column field="gracePeriod" header="Período de gracia"></pv-column>
              <pv-column field="initialBalance" header="Saldo inicial"></pv-column>
              <pv-column field="indexedInitialBalance" header="Saldo inicial indexado"></pv-column>
              <pv-column field="interest" header="Interés"></pv-column>
              <pv-column field="fee" header="Cuota"></pv-column>
              <pv-column field="amortization" header="Amortización"></pv-column>
              <pv-column field="creditLifeInsurance" header="Seguro de desgravamen"></pv-column>
              <pv-column field="vehicleInsurance" header="Seguro vehicular"></pv-column>
              <pv-column field="vehicleInsurance" header="Saldo final"></pv-column>
              <pv-column field="flow" header="Flujo"></pv-column>
            </pv-data-table>
          </div>
        </div>
      </template>
    </pv-card>
  </div>

</template>

<style scoped>
:deep(th) {
  background-color: var(--red) !important;
  color: var(--white) !important;
}

.division {
  border-top: 2px solid var(--red);
  margin-bottom: 8px;
  margin-top: 8px;
}
</style>