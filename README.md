# Projeto: Banco de Dados para Loja Online

**Objetivo Geral:** Criar a estrutura de dados para gerenciar clientes, produtos e os pedidos realizados em um e-commerce.
**Público-Alvo:** Administradores da loja que precisam controlar o estoque e o histórico de compras dos usuários.

## Modelo de Dados (Diagrama ER)
```mermaid
erDiagram
    CLIENTES ||--o{ PEDIDOS : faz
    PRODUTOS ||--o{ PEDIDOS : "está no"
    
    CLIENTES {
        int id_cliente PK
        string nome
        string email
    }
    PRODUTOS {
        int id_produto PK
        string nome_produto
        float preco
    }
    PEDIDOS {
        int id_pedido PK
        int id_cliente FK
        int id_produto FK
        date data_compra
    }
