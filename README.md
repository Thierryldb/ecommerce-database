1. Visão Geral
Este projeto consiste no desenvolvimento de um sistema em Java para o gerenciamento de estoque de um armazém logístico de e-commerce (similar ao Mercado Livre). O sistema opera via console e permite o cadastro, consulta, atualização e ordenação de produtos, focando na aplicação prática de estruturas de dados e algoritmos de ordenação e busca em memória.

2. Decisões Técnicas e Estruturas de Dados
Para atender aos objetivos de aprendizado e otimização de recursos, foram utilizadas as seguintes estratégias:

Persistência em Memória: O sistema não utiliza Banco de Dados (SGBD). Os dados são mantidos em memória durante a execução.

HashMap (Tabela Hash): Utilizado para o armazenamento principal dos produtos indexados pelo código.

Justificativa: Otimização de tempo. A busca por código em uma Tabela Hash possui complexidade O(1) (constante), sendo muito mais rápida que varrer uma lista.

ArrayList (Lista Dinâmica): Utilizada para manter uma coleção sequencial dos produtos.

Justificativa: Facilita operações de iteração para listagens completas e aplicação de algoritmos de ordenação.

3. Algoritmos Implementados
A. Algoritmos de Busca
Busca Otimizada (Hash): Usada na pesquisa por Código. Acessa o objeto diretamente na memória sem precisar percorrer a lista.

Busca Linear (Linear Search): Implementada para as pesquisas por Nome e Categoria. O algoritmo percorre a lista (O(n)) verificando se cada item corresponde ao critério (ex: uso de contains para nomes parciais).

B. Algoritmos de Ordenação
Bubble Sort (Implementação Manual): Foi implementado manualmente o algoritmo Bubble Sort para a ordenação por critério de Preço.

Objetivo: Demonstrar conhecimento na lógica de construção de algoritmos de ordenação baseados em comparação e troca (swap).

TimSort/MergeSort (Nativo): Para os critérios de Popularidade e Avaliação, utilizou-se o Collections.sort (que implementa TimSort), demonstrando o uso eficiente de bibliotecas padrão da linguagem.

4. Arquitetura do Projeto
O projeto foi modularizado em três classes principais para garantir a separação de responsabilidades (Modularização e Abstração):

Produto.java (Modelo/Entidade):

Representa o objeto do mundo real. Contém os atributos (código, nome, preço, etc.), construtores e métodos de acesso (getters/setters).

Estoque.java (Regra de Negócio e Estrutura de Dados):

É o "cérebro" do sistema. Gerencia o HashMap e o ArrayList. Contém a implementação dos algoritmos de busca e o método bubbleSort manual.

SistemaGerenciamento.java (Interface/View):

Responsável pela interação com o usuário via Console. Gerencia o menu, captura a entrada de dados (classe Scanner) e trata exceções de entrada.

5. Funcionalidades
✅ Cadastrar Produto: Insere novos itens verificando duplicidade de código instantaneamente.

✅ Listar Todos: Exibe o inventário completo.

✅ Atualizar Estoque: Modifica a quantidade de um item específico.

✅ Pesquisar:

Por Código (Exato e Rápido).

Por Nome (Parcial).

Por Categoria.

✅ Ordenar: Organiza a visualização por Popularidade, Quantidade, Preço (Bubble Sort) ou Avaliação.
