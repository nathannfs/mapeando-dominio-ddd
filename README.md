# Sistema de Gerenciamento de Estoque

## Entidades de Domínio

1. **Produto**
   - Atributos:
     - ID único
     - Nome
     - Tamanho
     - Cor
     - Quantidade em estoque
     - Quantidade mínima de estoque
   - Relacionamentos:
     - Histórico de movimentações
     - Histórico de vendas

2. **Estoque**
   - Atributos:
     - Lista de produtos
     - Quantidade total de produtos
     - Alertas de estoque mínimo
   - Relacionamentos:
     - Produtos
     - Histórico de vendas

3. **Histórico de Vendas**
   - Atributos:
     - Produto vendido
     - Quantidade vendida
     - Data da venda
     - Lucro gerado
   - Relacionamentos:
     - Produto

4. **Ordem de Compra**
   - Atributos:
     - Produto a ser comprado
     - Quantidade a ser comprada
     - Fornecedor
     - Prazo de entrega
     - Status da ordem (pendente, concluída, etc.)
   - Relacionamentos:
     - Produto
     - Fornecedor

5. **Fornecedor**
   - Atributos:
     - Nome
     - Informações de contato
     - Prazos de entrega
   - Relacionamentos:
     - Ordens de compra

6. **Alerta**
   - Atributos:
     - Produto relacionado
     - Mensagem de alerta (estoque mínimo atingido)
     - Método de envio (e-mail, notificação no sistema)
   - Relacionamentos:
     - Produto

---

## Casos de Uso

1. **Rastrear Produto Individualmente**
   - Ação: Atribuir um número de identificação único a cada produto e rastrear suas movimentações.
   - Entidades envolvidas: Produto, Estoque.

2. **Definir Quantidade Mínima de Estoque**
   - Ação: Permitir que o usuário defina um limite mínimo de estoque para cada produto.
   - Entidades envolvidas: Produto, Estoque.

3. **Receber Alertas de Estoque Baixo**
   - Ação: Enviar alertas por e-mail e notificação no sistema quando o estoque de um produto estiver próximo do limite mínimo.
   - Entidades envolvidas: Produto, Estoque, Alerta.

4. **Visualizar Histórico de Vendas**
   - Ação: Exibir informações sobre vendas passadas, como quantidade vendida, lucro gerado e produtos mais vendidos.
   - Entidades envolvidas: Histórico de Vendas, Produto.

5. **Visualizar Tendências de Estoque**
   - Ação: Mostrar gráficos ou relatórios sobre as tendências de estoque ao longo do tempo.
   - Entidades envolvidas: Estoque, Produto, Histórico de Vendas.

6. **Criar e Gerenciar Ordens de Compra**
   - Ação: Gerar ordens de compra automaticamente com base nas quantidades mínimas de estoque e tendências de vendas.
   - Entidades envolvidas: Ordem de Compra, Produto, Fornecedor.

7. **Integrar com Fornecedores**
   - Ação: Receber atualizações automáticas sobre prazos de entrega de novas remessas.
   - Entidades envolvidas: Fornecedor, Ordem de Compra.

8. **Adicionar Informações Detalhadas do Produto**
   - Ação: Permitir a inclusão de informações adicionais, como tamanho e cor, para melhorar o rastreamento.
   - Entidades envolvidas: Produto.

9. **Visualizar Lucro por Produto**
   - Ação: Mostrar o lucro gerado por cada produto em um determinado período.
   - Entidades envolvidas: Histórico de Vendas, Produto.

10. **Monitorar Produtos Populares**
    - Ação: Identificar e exibir os produtos mais vendidos em um período específico.
    - Entidades envolvidas: Histórico de Vendas, Produto.
