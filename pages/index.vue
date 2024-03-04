<!-- components/PythonPetsMasterClass.vue -->
<template>
    <div class="container">
      <section class="header">
        <h1 class="text-center mt-5">PythonPets MasterClass</h1>
  
        <!-- Adicionando imagens de cães e gatos no laptop -->
        <div class="row mt-3">
          <div class="col-12 col-md-6">
            <img
              src="/cat.png"
              alt="Gato no Laptop"
              class="img-thumbnail rounded mb-3"
            />
          </div>
          <div class="col-12 col-md-6">
            <img
              src="/dog.png"
              alt="Cão no Laptop"
              class="img-thumbnail rounded"
            />
          </div>
        </div>
      </section>
      <section class="section mt-4">
        <div class="feature-box">
          <p>
            <strong>PythonPets MasterClass</strong> é um curso online que promete
            transformar seu animal de estimação em um guru da codificação. Seu
            bichinho está prestes a se tornar o próximo prodígio da programação!
          </p>
  
          <h2 class="mt-3">Conteúdo do Curso:</h2>
          <ul>
            <li>Introdução ao Python para Pets</li>
            <li>
              Orientações sobre como escolher o laptop perfeito para seu bichinho
            </li>
            <li>Exercícios práticos de codificação com patinhas (ou garras)</li>
            <li>Como criar um site canino em Django</li>
          </ul>
        </div>
      </section>
  
      <section class="section mt-4">
        <div class="feature-box">
          <h2>Bônus Inusitado:</h2>
          <p>
            Incluímos um módulo especial sobre como treinar seu animal de
            estimação para resolver problemas do dia a dia usando algoritmos
            complexos. Afinal, quem não quer um cão ou gato que possa otimizar a
            distribuição de brinquedos pela casa?
          </p>
        </div>
      </section>
  
      <section class="section feature-box">
        <div class="container mt-5">
          <div class="jumbotron text-center">
            <h1 class="display-4">PythonPets MasterClass</h1>
            <p class="lead">
              Transforme a relação com seus animais de estimação através da
              programação em Python!
            </p>
          </div>
  
          <div class="row justify-content-center">
            <div class="col-md-6">
              <div class="card text-center">
                <div class="card-header">
                  <h2>Preço Especial de Lançamento</h2>
                </div>
                <div class="card-body">
                  <h3 class="card-title">R$ 999,99</h3>
                  <p class="card-text">
                    Inscreva-se agora e tenha acesso a todos os benefícios do
                    curso.
                  </p>
                  <button @click="navigateTo('/checkout')" class="btn btn-lg cta-button">Inscreva-se Agora</button>
                </div>
                <div class="card-footer text-muted">
                  * Preço promocional válido até
                  {{ new Date().toLocaleDateString() }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <footer class="footer mt-auto py-3 bg-light">
        <div class="container text-center">
          <p class="text-muted">
            ** Este curso é uma criação fictícia destinada apenas para fins
            humorísticos e não representa um curso real. **
          </p>
        </div>
      </footer>
    </div>
  </template>
  
  <script setup></script>
  
  <style>
  body {
    font-family: "Roboto", sans-serif;
    background-color: #2c3e50;
    color: #333;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
  }
  
  .header {
    background-color: #2c3e50;
    color: #ecf0f1;
    padding: 20px;
    text-align: center;
  }
  
  .section {
    margin: 40px 0;
  }
  
  .section h2 {
    color: #3498db;
  }
  
  .feature-box {
    border: 1px solid #bdc3c7;
    background-color: #ecf0f1;
    padding: 20px;
    margin-bottom: 20px;
  }
  
  .feature-box h3 {
    color: #3498db;
  }
  
  .cta-button {
    display: inline-block;
    background-color: #e74c3c;
    color: #fff;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    transition: background-color 0.3s ease;
  }
  
  .cta-button:hover {
    background-color: #c0392b;
  }
  
  .footer {
    background-color: #34495e;
    color: #ecf0f1;
    padding: 10px;
    text-align: center;
  }
  </style>
  