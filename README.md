# powerapps-google-maps-connector
Custom connectors for Power Apps to integrate with Google Maps Routes and Geocoding APIs
# Power Apps: Calculadora de Rotas com API do Google Maps

## Resumo do Projeto

Este projeto demonstra a criação e utilização de conectores customizados no Microsoft Power Apps para integração com a plataforma Google Maps. O objetivo foi desenvolver um aplicativo capaz de calcular a rota mais eficiente entre dois pontos, retornando a distância em milhas, a duração da viagem e os custos de pedágio.

## Funcionalidades Implementadas

* **Dois Conectores Customizados:** Um para a API de Geocodificação (`maps.googleapis.com`) e outro para a API de Rotas (`routes.googleapis.com`), cujos arquivos de definição (`.json`) estão neste repositório.
* **Cálculo de Rota:** Utiliza a API de Rotas para obter o trajeto otimizado.
* **Cálculo de Pedágio:** Configurado para solicitar e exibir informações de pedágio (`TOLLS`).
* **Unidades Customizadas:** A resposta é solicitada em unidades imperiais (milhas).

## Tecnologias Utilizadas

* Microsoft Power Apps
* Power Apps Custom Connectors
* Google Cloud Platform
* Google Maps Geocoding API
* Google Maps Routes API

## Desafios e Aprendizados

Durante o desenvolvimento, vários desafios foram superados, demonstrando habilidades avançadas de depuração e solução de problemas de integração de APIs:

-   **Diagnóstico de Erros de API:** Análise de múltiplos códigos de erro (400, 403, 404) para identificar a causa raiz de problemas de permissão, URLs incorretas e argumentos inválidos.
-   **Restrições de Host do Conector:** Descoberta de que um único conector não podia atender a dois hosts de API diferentes (`maps.googleapis.com` e `routes.googleapis.com`), o que exigiu uma refatoração da arquitetura para dois conectores especializados.
-   **Parâmetros de Autenticação:** Identificação de que diferentes APIs do Google podem ter sensibilidades distintas ao nome do parâmetro da chave (`key` vs. `Key`), necessitando de testes e ajustes finos.
-   **Requisitos Específicos da API:** Implementação de parâmetros e cabeçalhos obrigatórios da API de Rotas, como o `extraComputations` e o `X-Goog-FieldMask`, que não são imediatamente óbvios.
