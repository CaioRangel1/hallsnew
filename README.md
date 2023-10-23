# Projeto Nimbus - HALLS

## Apresentação da empresa :cloud_with_lightning_and_rain:
A empresa NIMBUS é uma provedora de serviços e dados meteorológicos líder no setor. Ela coleta informações meteorológicas de diversas fontes, incluindo satélites, radares, estações terrestres e boias oceânicas. A NIMBUS oferece uma ampla gama de serviços, como previsões meteorológicas precisas, consultoria meteorológica especializada e soluções personalizadas para atender às necessidades de diferentes setores, como agricultura, aviação, energia e muito mais. A empresa se destaca por sua tecnologia de ponta, ampla rede de coleta de dados e capacidade de fornecer informações climáticas em tempo real em todos os estados de atuação (hoje são Rio de Janeiro e São Paulo). Seus serviços são acessíveis por meio de assinaturas, contratos corporativos, APIs e outras formas de acesso, tornando-os valiosos para uma variedade de clientes e aplicações. Hoje a empresa é formada por apenas 6 pessoas. 

## 5W2H :thread:

#### Quem?

- O **sistema** que será criado, será um sistema baseado em filtro e uso dos dados, para fornecer previsão aos clientes interessados no resultado dessa procura, clientes como empreiteiras, canteiros de obras, etc.

#### Como ? 

- O **sistema** vai utilizar os dados capturados para gerar cálculos estáticos, preenchimento dos gráficos e amostragem de resultados atuais e futuros sobre condições meteorológicas.

#### O quê ?

- O **sistema** irá disponibilizar condições climáticas nas áreas de atuação da NIMBUS.

#### Quanto ? 

- A princípio o custo geral do **sistema** será relacionado ao tempo dedicado ao projeto.

#### Onde?

- O **sistema** irá funcionar por serviço online, atendendo os clientes através de uma aplicação WEB.


#### Por quê?

- O **sistema** terá a utilidade de melhorar a funcionalidade do Site afim de apresentar uma plataforma com mais mecanismos para atender os clientes da Nimbus. A necessidade atual da empresa, e tanto e melhorias estéticas quanto funcionais, por isso a necessidade da criação de um sistema mais robustos com o uso desses dados.

#### Quando?

- Os dados usados no **sistema** são absorvidos em todo tempo e momento. Mas a consulta é feita e realizada dentro do horário de trabalho do cliente, podendo ser horário comercial e até 24 horas por dia.

## Quais dados e qual formato? :game_die:

- o retorno é em relação a ultima medida de cada estação em modelo JSON, CSV e PNG
- As estações apresentam variáveis diferentes, algumas meteorológicas, outras pluviometrias outras oceânicas, sendo assim cada uma passa dados diferentes e sendo assim podendo receber dados e variáveis diferentes.
- Não tem uma tabela com as variáveis, elas estão no sistema de maneira constante, mostradas diretamente no sistema.
- Tem até variáveis que não estão em utilização como de radiação solar, pois não tem clientes de energia solar.
- O sistema tem um limite de 15 dias, após isso e necessário criar um relatório para a consulta dos dados.

## Visão geral do escopo do sistema? 

- Previsão e alerta meteorológicos em diversas localizações geográficas, Acompanhamento, rastreamento e registro de eventos meteorolicos.Coleta e análise de dados com armazenamento de históricos passiveis de apoio a tomada de decisões na gestão de diversos setores como agricultura, aviação, energia e gestão de desastres naturais.

## Objetos manipulados pelo sistema?

- Dados meteorológicos, Dados históricos, Previsões, Mapas e Gráficos, Alertas Meteorológicos.

#### Restrições a serem obedecidas?

- Imprecisão e morosidade nas previsões e alertas climaticos. Inconsistencia e lentidão nos dados historicos. Segurança e integridade dos dados.


# Requisitos funcionais: :man_technologist:

  - O **sistema** deve criar Gráficos e tabelas que serão mais interativos para o usuário  
  - O **sistema** deve apresentar seleção de data/período desejado (dentro do período disponibilizado pela Nimbus de 15 dias) 
  - O **sistema** deve mostrar somente datas com dados desejada pelo usuário como (temperatura, pluviosidade, entre outros.) 
  - O **sistema** deve ter mapas que serão interativos, quando a setinha do mouse estiver em cima de alguma área do mapa (que é disponibilizado pela Nimbus) irá mostrar os dados e as estações meteorológica, pluviais, oceânicas e outras.
  - O **sistema** deve permitir a exportação em csv, pdf ou png
  - O **sistema** deve permitir a busca de dados específicos
  - O **sistema** deve possibilitar a escolha das variáveis a serem exibidas simultaneamente
  - O **sistema** deve permitir desenhar formas no mapa para possibilitar múltiplos marcadores

# Requisitos não funcionais:

  - O **sistema** deve ter uma aplicação mobile
  - O **sistema** deve ser feito em react
  - O **sistema** deve ficar disponivel 24 horas

# Propósito :thumbsup:
O **sistema** tem como propósito ter uma página para exibição, tratamento e requisição dos dados, um mapa interativo, com tipos diferentes de seleção e apresentação dos dados de acordo com a necessidade do usuário, e também tornar os gráficos mais dinâmicos e apôs finalizado, ter uma otimização estética

# Casos de uso:

  ### Nome: visualisar dados
  - Atores: usuário
  - pré-condições: acessar o site e fazer login
  - Fluxo básico:
    * o usuário acessa a opção ''analise de dados''
    * o usuário seleciona o tipo de vizualização desejado
       * gráfico
       * tabela
       * mapa
    * o usuário configura os filtros do sistema
       * Data inicial
       * Data final
       * Tipos de variáves meteorologias
       * Estação de monitoramento
       * Frequência
       * Operação matemática utilizada
    * o sistema mostra os dados filtrados pelo usuário
  - Pos-condições:
    * os dados são apresentados ao usuário
    * a interação é realizada com sucesso

  
  ### Nome: exportar dados
  - Atores: usuário
  - pré-condições: acessar o site e fazer login
  - Fluxo básico:
    * o usuário acessa a opção ''analise de dados''
    * o usuário seleciona o tipo de vizualização desejado
       * gráfico
       * tabela
       * mapa
    * o usuário configura os filtros do sistema
       * Data inicial
       * Data final
       * Tipos de variáves meteorologias
       * Estação de monitoramento
       * Frequência
       * Operação matemática utilizada
    * o sistema mostra os dados filtrados pelo usuário
    * o usuário seleciona o tipo de exportação desejado
       * CSV
       * PNG
       * PDF
  - Pos-condições:
    * os dados são apresentados ao usuário
    * o usuário realiza o download dos dados no formato selecionado
    * a interação é realizada com sucesso
   
    
  ### Nome: interagir com mapa
  - Atores: usuário
  - pré-condições: acessar o site e fazer login
  - fluxo básico:
    * O usuário acessa a opção "mapas"
    * O usuário seleciona um ponto ou uma área do mapa
  - Pós-condições:
    * Os pontos selecionados mudam de cor e apresentam o historico de dados dos pontos selecioandos
    * A interação é realizada com sucesso

  ### Link do repositorio: https://github.com/CaioRangel1/hallsnew
      
### Participantes :trophy: 
- Márcio Moreira
- Douglas da Silva
- João Victor Bathomarco
- Vitor Ribeiro
- Caio Rangel 
