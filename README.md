# RESTful API para Ponto de Vendas (frente de caixa) 

API para um PDV (Frente de Caixa), criada em Javascript, Banco de Dados Postgres, criptografia de senha usando o JSON Web Token, com deploy na Amazon hospedagem AWS.
A API permite que o usuário faça as seguintes operações:

- Fazer Login
- Cadastrar Usuário
- Detalhar Perfil do Usuário Logado
- Editar Perfil do Usuário Logado
- Listar categorias
- Listar Produtos
- Detalhar Produtos
- Excluir Produtos
- Cadastrar Produtos
- Editar Produtos
- Cadastrar Cliente
- Editar Cliente
- Listar Clientes
- Detalhar Cliente
- Cadastar Pedido
- Listar Pedidos
- Listar Pedidos Por Cliente


## Informações sobre o sistema:


### **Rotas disponíveis**

```javascript
rotas.post("/usuario", validarCorpoRequisicao(schemaUsuario), cadastrarUsuario);
rotas.post("/login", validarCorpoRequisicao(schemaLogin), efetuarLogin);
rotas.get("/categoria", listarCategorias);

rotas.get("/usuario", detalharUsuarioLogado);
rotas.put("/usuario", validarCorpoRequisicao(schemaUsuario), editarUsuarioLogado);

rotas.get("/produto", listarProduto);
rotas.get("/produto/:id", detalharProduto);
rotas.delete("/produto/:id", multer.single('produto_imagem'), excluirProduto);
rotas.post("/produto", multer.single('produto_imagem'), validarCorpoRequisicao(schemaProdutos), cadastrarProduto);
rotas.put("/produto/:id", multer.single('produto_imagem'), validarCorpoRequisicao(schemaProdutos), editarProduto);

rotas.post("/cliente", validarCorpoRequisicao(schemaCliente), cadastrarCliente);
rotas.put("/cliente/:id", validarCorpoRequisicao(schemaCliente), editarCliente);
rotas.get("/cliente", listarClientes);
rotas.get("/cliente/:id", detalharCliente);

rotas.post("/pedido",validarCorpoRequisicao(schemaPedidos), cadastarPedido);
rotas.get("/pedido", listarpedidos); 
rotas.get("/pedido/:id", pedidosPorCliente);
```
