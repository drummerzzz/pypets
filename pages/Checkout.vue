<template>
  <div class="container mt-5">
    <div
      v-if="loading"
      class="d-flex justify-content-center align-items-center vh-100"
    >
      <div class="spinner-border text-primary" role="status">
        <span class="visually-hidden">Carregando...</span>
      </div>
    </div>
    <div v-else class="row section feature-box needs-validation" novalidate>
      <div class="col-md-6">
        <h4 class="mb-3">Detalhes de Pagamento</h4>
        <div class="row">
          <div class="col-md-12 mb-3">
            <label for="firstName">Nome Completo</label>
            <input
              type="text"
              class="form-control"
              id="firstName"
              placeholder="Seu nome"
              value="JOAO DA SILVA"
              required
            />
            <div class="invalid-feedback">
              É obrigatório preencher seu nome.
            </div>
          </div>
        </div>

        <div class="mb-3">
          <label for="email">Email</label>
          <input
            type="email"
            class="form-control"
            id="email"
            placeholder="seu@email.com"
            value="irineu@tunaosabenem.eu"
            required
          />
          <div class="invalid-feedback">
            Por favor, insira um endereço de e-mail válido.
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="country">País</label>
            <input
              type="text"
              class="form-control"
              id="country"
              placeholder="BR"
              required
              value="BR"
            />
            <div class="invalid-feedback">Por favor, insira o país.</div>
          </div>
          <div class="col-md-6 mb-3">
            <label for="state">Estado</label>
            <input
              type="text"
              class="form-control"
              id="state"
              placeholder="Rio de Janeiro"
              required
              value="Rio de Janeiro"
            />
            <div class="invalid-feedback">Por favor, insira o estado.</div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="city">Cidade</label>
            <input
              type="text"
              class="form-control"
              id="city"
              placeholder="Rio de Janeiro"
              required
              value="Rio de Janeiro"
            />
            <div class="invalid-feedback">Por favor, insira a cidade.</div>
          </div>
          <div class="col-md-6 mb-3">
            <label for="district">Bairro</label>
            <input
              type="text"
              class="form-control"
              id="district"
              placeholder="Leblon"
              required
              value="Leblon"
            />
            <div class="invalid-feedback">Por favor, insira o bairro.</div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="zipCode">CEP</label>
            <input
              type="text"
              class="form-control"
              id="zipCode"
              placeholder="25650011"
              required
              value="25650011"
            />
            <div class="invalid-feedback">Por favor, insira o CEP.</div>
          </div>
          <div class="col-md-6 mb-3">
            <label for="street">Rua</label>
            <input
              type="text"
              class="form-control"
              id="street"
              placeholder="Av Geraldo Cardoso"
              required
              value="Av Geraldo Cardoso"
            />
            <div class="invalid-feedback">Por favor, insira a rua.</div>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <hr class="mb-4" />

        <h4 class="mb-3">Pagamento</h4>

        <div class="row">
          <div class="col-md-12 mb-3">
            <label for="cc-name">Nome no Cartão</label>
            <input
              type="text"
              class="form-control"
              id="cc-name"
              placeholder=""
              value="JOAO DA SILVA"
              required
            />
            <div class="invalid-feedback">O nome no cartão é obrigatório.</div>
          </div>
          <div class="col-md-12 mb-3">
            <label for="cc-number">Número do Cartão de Crédito</label>
            <input
              type="text"
              class="form-control"
              id="cc-number"
              placeholder=""
              value="5261424250184574"
              required
            />
            <div class="invalid-feedback">
              O número do cartão de crédito é obrigatório.
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-md-6 mb-3">
            <label for="cc-expiration">Data de Validade</label>
            <input
              type="text"
              class="form-control"
              id="cc-expiration"
              placeholder=""
              value="06/2028"
              required
            />
            <div class="invalid-feedback">
              A data de validade é obrigatória.
            </div>
          </div>
          <div class="col-md-6 mb-3">
            <label for="cc-cvv">CVV</label>
            <input
              type="text"
              class="form-control"
              id="cc-cvv"
              placeholder=""
              value="321"
              required
            />
            <div class="invalid-feedback">
              O código de segurança é obrigatório.
            </div>
          </div>
        </div>

        <hr class="mb-4" />
        <div class="row">
          <button
            class="btn btn-primary btn-lg btn-block"
            @click="() => createCharge()"
          >
            Finalizar Pagamento
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";

const loading = ref(false);

const createCharge = async () => {
  loading.value = !loading.value;
  const headers = {
    Accept: "*/*",
    "X-Api-Key": "d2a64cfb-d120-45b2-ace6-ec3cc11b537b",
    "X-Client-Id": "4223fb1a-cf75-4ba3-8bbf-585371943a91",
    "Content-Type": "application/json",
  };

  const data = JSON.stringify({
    appInfo: {
      platform: {
        integrator: "malga",
        name: "pluging-vtex-ppp",
        version: "1.12",
      },
      device: {
        name: window.navigator.platform,
        version: window.navigator.appVersion,
      },
      system: {
        name: "PyPet", // Coloque a lógica para obter o nome do sistema aqui, se necessário
        version: "13.12", // Coloque a lógica para obter a versão do sistema aqui, se necessário
      },
    },
    merchantId: "3ee59352-120d-45ce-ad66-727a85ac8690",
    amount: 150,
    currency: "BRL",
    statementDescriptor: "LOJA JOAO",
    description: "Descrição longa da cobrança",
    capture: false,
    orderId: "32c68ff7-902c-408b-b464-cf487c7cda97",
    paymentMethod: {
      paymentType: "credit",
      installments: 1,
    },
    paymentSource: {
      sourceType: "card",
      card: {
        cardNumber: "4636496958100111",
        cardCvv: "120",
        cardExpirationDate: "09/2027",
        cardHolderName: "JOAO DA SILVA",
      },
    },
  });

  const response = await axios.request({
    url: "https://sandbox-api.dev.malga.io/v1/charges",
    method: "POST",
    headers,
    data,
  });

  if (response.status === 201) {
    await navigateTo("success");
  } else {
    alert(response.statusText);
    console.log(response.data);
    loading.value = !loading.value;
  }
};
</script>
