<template>
  <div id="painelLancamento">
    <div id="formularioLancamento">
      <form>
        <div id="tiposLancamento">
          <input type="radio" name="tipo" id="entrada" />
          <label for="entrada" class="entrada">Entrada</label>
          <input type="radio" name="tipo" id="saida" />
          <label for="saida" class="gasto">Saída</label>
        </div>

        <label for="valor">Valor</label>
        <input type="number" name="valor" id="valor" />
        <label for="descricao">Descrição</label>
        <input type="text" name="descricao" id="descricao" />
        <label for="data">Data</label>
        <input type="date" name="data" id="data" />

        <button>Lançar</button>
      </form>
    </div>

    <div id="areaLancamentos">
      <BlocoLancamento
        tipo="entrada"
        :lancamento="{
          valor: 100,
          descricao: 'Venda de HQ',
          data: '2020-10-20',
        }"
      />

      <BlocoLancamento
        tipo="saida"
        :lancamento="{
          valor: 50,
          descricao: 'Mercado',
          data: '2020-10-18',
        }"
      />

      <BlocoLancamento
        tipo="saida"
        :lancamento="{
          valor: 10,
          descricao: 'Farmácia',
          data: '2020-09-17',
        }"
      />
    </div>
  </div>
</template>

<script>
import BlocoLancamento from "./BlocoLancamento.vue";
export default {
  name: "PainelLancamento",
  components: {
    BlocoLancamento,
  },
};
</script>

<style scoped>
#painelLancamento {
  width: 40%;
  padding: 10px;
}

#formularioLancamento {
  background-color: white;
  border-radius: 20px;
  padding: 20px;
  font-family: "padrao";
}

#valor,
#descricao,
#data,
button {
  display: block;
  margin-bottom: 10px;
}

#valor,
#descricao,
#data {
  height: 25px;
  font-family: "padrao";
  font-size: 100%;
  border: 1px solid #cccccc;
  border-radius: 5px;
  outline: none;
}

#tiposLancamento {
  margin-bottom: 20px;
  font-family: "negrito";
  font-size: 110%;
}

#tiposLancamento label {
  margin-right: 20px;
}

#descricao {
  width: 70%;
}

button {
  background-color: var(--cor-destaque);
  border: none;
  outline: none;
  border-radius: 5px;
  padding: 10px 20px;
  color: white;
  font-family: "negrito";
  font-size: 120%;
}

#areaLancamentos {
  margin-top: 30px;
}
</style>