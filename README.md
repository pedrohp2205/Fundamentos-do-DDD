# 📦 Sistema de Gerenciamento de Estoque

## Entidades de Domínio

### Produto
- `id`: Identificador único
- `nome`: Nome do produto
- `descrição`: Informações complementares
- `tamanho`: Tamanho (se aplicável)
- `cor`: Cor (se aplicável)
- `preço_custo`: Valor de compra
- `preço_venda`: Valor de venda
- `estoque_atual`: Quantidade atual disponível
- `estoque_mínimo`: Quantidade mínima para gerar alerta

### Estoque
- `id`
- `produto_id`: Referência ao produto
- `quantidade`: Quantidade movimentada
- `data_movimentação`: Data da entrada ou saída
- `tipo`: Entrada ou Saída

### Venda
- `id`
- `produtos`: Lista de produtos vendidos com quantidade
- `data`: Data da venda
- `valor_total`
- `lucro_total`

### Alerta
- `id`
- `produto_id`
- `data_geração`
- `tipo`: Estoque baixo, produto em falta, etc.
- `status`: Ativo ou resolvido

### Ordem de Compra
- `id`
- `produtos`: Lista de produtos e quantidades
- `data_criação`
- `status`: Pendente, enviado, recebido
- `fornecedor_id`: Referência ao fornecedor (opcional)

### Fornecedor (futuramente integrável)
- `id`
- `nome`
- `contato`
- `produtos_fornecidos`
- `prazo_entrega`

---

## Casos de Uso

### Gerenciamento de Produtos
- Cadastrar produto
- Editar produto
- Remover produto
- Listar produtos
- Consultar produto por ID

### Gerenciamento de Estoque
- Adicionar produto ao estoque (entrada)
- Remover produto do estoque (saída)
- Registrar movimentações
- Consultar histórico de movimentações

### Gestão de Alertas
- Verificar estoque mínimo automaticamente
- Gerar alerta de estoque baixo
- Enviar alerta por e-mail e/ou sistema
- Listar alertas ativos

### Gestão de Vendas
- Registrar nova venda
- Listar vendas por período
- Calcular lucro por produto
- Identificar produtos mais vendidos

### Visualização de Relatórios
- Relatório de vendas por período
- Relatório de lucro por produto
- Relatório de movimentações de estoque
- Análise de tendências de venda e estoque

### Gestão de Ordens de Compra
- Criar ordem de compra automaticamente
- Listar ordens de compra
- Atualizar status das ordens
- Integrar com fornecedores (prazos, status de entrega)

---

## Notificações
- Envio de alertas via e-mail
- Exibição de notificações internas no sistema
- Controle de status (lida, não lida)

---

## 🔐 (Opcional) Usuários
- `id`
- `nome`
- `e-mail`
- `permissões`
