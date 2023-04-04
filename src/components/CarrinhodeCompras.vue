<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <div class="text-center">
          <h1 class="display-4" >Carrinho de Compras</h1>
        </div>
        <form>
          <div class="form-group">
            <label>Descrição:</label>
            <input v-model="descricao" class="form-control" />
          </div>
          <div class="form-group">
            <label>Valor Unitário:</label>
            <input v-model.number="valorUnitario" type="number" class="form-control" />
          </div>
          <div class="form-group">
            <label>Quantidade:</label>
            <input v-model.number="quantidade" type="number" class="form-control" />
          </div>
          <div class="form-group">
            <button @click.prevent="adicionar" class="btn btn-primary">Adicionar</button>
          </div>
        </form>
        <table class="table">
          <thead>
            <tr>
              <th>Descrição</th>
              <th>Valor Unitário</th>
              <th>Quantidade</th>
              <th>Total</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(produto, index) in produtos" :key="index">
              <td>{{ produto.descricao }}</td>
              <td>{{ produto.valorUnitario }}</td>
              <td>{{ produto.quantidade }}</td>
              <td>{{ produto.total }}</td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td colspan="3" id="total"><strong>Total:</strong></td>
              <td>
                <strong>{{ total.toFixed(2) }}</strong>
              </td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CarrinhoDeCompras",
  data() {
    return {
      descricao: "",
      valorUnitario: 0,
      quantidade: 0,
      produtos: [],
    };
  },
  computed: {
    total() {
      return this.produtos.reduce((aux, produto) => aux + produto.total, 0);
    },
  },
  methods: {
    adicionar() {
      let novoProduto = {
        descricao: this.descricao,
        valorUnitario: this.valorUnitario,
        quantidade: this.quantidade,
        total: this.valorUnitario * this.quantidade,
      };

      this.produtos.push(novoProduto);

      this.descricao = "";
      this.valorUnitario = 0;
      this.quantidade = 0;
    },
  },
};
</script>

<style>
#total {
  text-align: right;
}
</style>
