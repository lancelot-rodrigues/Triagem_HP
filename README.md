# Projeto de Classificação de Anúncios de Cartuchos HP

Este repositório contém o desenvolvimento de um sistema para analisar e classificar anúncios de cartuchos de impressora HP em plataformas de comércio eletrônico. O projeto foi dividido em duas fases principais: extração de atributos e construção de um classificador inteligente.

## Resumo do Projeto

O objetivo deste trabalho foi criar uma solução automatizada para identificar a natureza dos anúncios de cartuchos HP, distinguindo produtos originais de produtos não originais (compatíveis, remanufaturados) ou suspeitos. Para isso, foi desenvolvido um conjunto de etapas que:

**Extrai Atributos Estruturados**  
Utiliza modelos de linguagem para ler as descrições dos anúncios e extrair informações importantes, como o modelo, a marca declarada, a originalidade e uma nota de qualidade da descrição.

**Enriquece os Dados**  
Gera novas características a partir das informações extraídas, como o nível de confiança no vendedor e o quanto o preço do anúncio se afasta da média do mercado para aquela categoria de produto.

**Classifica os Anúncios**  
Treina um modelo baseado em aprendizado de máquina usando essas características estruturadas para classificar cada anúncio nas categorias "Original" ou "Requer Atenção".

O classificador final apresentou um bom desempenho, alcançando uma taxa de acerto de 92 por cento ao distinguir os anúncios.

## Motivação e Aplicação Prática

O comércio eletrônico representa um desafio para marcas como a HP, pois há muitos anúncios de produtos não originais ou falsificados que podem enganar os consumidores e afetar a reputação da marca. Fazer esse tipo de análise manualmente em grande escala não é viável.

Este classificador foi criado com o objetivo de enfrentar esse problema com uma abordagem escalável e prática.

## Como o Classificador Pode Ajudar

**Triagem Automatizada e Otimização de Recursos**  
O sistema pode analisar milhares de anúncios por dia, funcionando como um filtro que separa os anúncios claramente originais daqueles que precisam de uma análise mais atenta.

**Criação de um Sistema de Alerta**  
É possível integrar o modelo a uma plataforma de acompanhamento. Anúncios classificados como "Requer Atenção" são direcionados a uma fila de revisão. A equipe responsável pode então se concentrar apenas nos casos mais relevantes, como entrar em contato com a plataforma para solicitar a remoção do anúncio ou investigar o vendedor.

**Análise Estratégica de Mercado**  
A partir dos dados classificados, a HP pode tirar conclusões úteis sobre o mercado. Por exemplo, identificar quais sites concentram mais anúncios duvidosos, quais modelos de cartuchos são mais utilizados por vendedores de produtos não originais e quais estratégias são usadas para fazer os produtos parecerem legítimos.

**Base para um Score de Risco**  
A chance calculada de um anúncio ser "Original" ou "Requer Atenção" pode ser transformada em uma pontuação de risco, de zero a cem. Isso serve para ordenar as prioridades de revisão. Por exemplo, anúncios com pontuação acima de noventa seriam analisados primeiro.

Este projeto oferece uma ferramenta útil para acompanhar e avaliar o mercado de forma eficiente, ajudando a proteger tanto os consumidores quanto a imagem da marca HP com base em dados concretos.

## Como Executar o Projeto

Este repositório contém o código necessário para executar o classificador de anúncios. Para reproduzir os resultados obtidos, siga os passos a seguir.

### Pré-requisitos

- Conta Google para utilizar o Google Colab
- Arquivo de dados chamado ml_produtos_hp_final_features_target.csv, que já possui os anúncios com as características organizadas

### Passos para Execução

**Acesse o Notebook**  
Abra o arquivo chamado Gen_AI_Sprint2.ipynb no Google Colab

**Faça o Upload do Arquivo de Dados**  
No painel lateral esquerdo do Colab, clique no ícone de pasta  
Selecione a opção para fazer upload de arquivo  
Escolha o arquivo ml_produtos_hp_final_features_target.csv do seu computador  
Espere até que o upload seja finalizado e o arquivo esteja visível no painel

**Execute as Células do Notebook**  
Com o arquivo carregado, execute as células do notebook  
A maneira mais direta é acessar o menu Ambiente de execução e selecionar Executar tudo  
O notebook vai carregar os dados, preparar as informações, treinar o modelo e ao final exibir os resultados com a taxa de acerto, a matriz de confusão e a importância de cada característica usada na análise
