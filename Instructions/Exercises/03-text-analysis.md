---
lab:
  title: Analisar texto no portal da Fábrica de IA do Azure
---

# Analisar texto no portal da Fábrica de IA do Azure

O Processamento de Linguagem Natural (NLP) é uma ramificação da IA que lida com a linguagem escrita e falada. Você pode usar o NLP para criar soluções que extraiam o significado semântico do texto ou da fala, ou que formulem respostas significativas em linguagem natural.

O serviço Linguagem de IA do Azure inclui Análise de Texto, com funcionalidades como reconhecimento de entidade, extração de frases-chave, resumo e análise de sentimento. Por exemplo, suponha que a agência de viagens fictícia Margie's Travel incentive os clientes a enviar avaliações de estadias em hotéis. Você pode usar o Serviço de linguagem para extrair entidades nomeadas, identificar frases-chave, resumir texto e muito mais.

Neste exercício, você usará a Linguagem de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para analisar avaliações de hotéis. 

Este exercício levará aproximadamente **20** minutos.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar. 

1. No navegador, navegue até `https://ai.azure.com/managementCenter/allResources` e clique em **Criar**. Em seguida, escolha a opção para criar um **recurso da Fábrica de IA do Azure**.

1. No assistente *Criar projeto*, insira um nome válido para o projeto.

1. Expanda *Opções avançadas* para especificar as seguintes configurações para o projeto:
    - **Assinatura:** sua assinatura do Azure
    - **Grupo de recursos**: crie ou selecione um grupo de recursos
    - **Região**: selecione um dos seguintes locais:
        * Leste dos EUA
        * França Central
        * Coreia Central
        * Europa Ocidental
        * Oeste dos EUA

    Selecione **Criar**. Aguarde até que seu projeto seja criado. Isso pode levar alguns minutos.

1. Quando o projeto for criado, a página *Visão geral* dos detalhes do projeto abrirá.

1. No menu à esquerda da tela, selecione **Playgrounds**. 

    >*Observação*: Expanda o menu para ler seu conteúdo clicando no ícone "expandir" superior.

1. Na página Playgrounds da Fábrica de IA do Azure, selecione **Experimentar o Playground de Linguagem**. O playground de linguagem é uma interface do usuário que permite experimentar alguns recursos da Linguagem de IA do Azure.  

## Extrair entidades nomeadas com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure

*Entidades nomeadas* são palavras que descrevem pessoas, lugares e objetos com nomes próprios. Vamos usar a funcionalidade de extração de entidade nomeada da Linguagem de IA do Azure para identificar tipos de informações em uma revisão.

1. No Playground Linguagem, selecione **Extrair informações**. Em seguida, selecione o bloco **Extrair entidades nomeadas**. 

1. Em *Amostra*, copie e cole a seguinte revisão:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selecione **Executar**. Examine a saída. Observe na seção *Detalhes* como as entidades extraídas vêm com informações adicionais, como pontuações de tipo e confiança. A pontuação de confiança representa a probabilidade de o tipo identificado realmente pertencer a essa categoria.

## Extrair frases-chave com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure

As *frases-chave* são as informações mais importantes no texto. Vamos usar a funcionalidade de extração de frases-chave da Linguagem de IA do Azure para extrair informações importantes de uma revisão.

1. No Playground Linguagem, selecione **Extrair informações**. Em seguida, selecione o bloco **Extrair frases-chave**. 

1. Em *Amostra*, copie e cole a seguinte revisão:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selecione **Executar**. Examine a saída. Observe as diferentes frases extraídas na seção *Detalhes*. Essas frases contribuirão mais para o significado do texto.

## Resumir texto com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure
 
1. Vejamos as funcionalidades de resumo da Linguagem de IA do Azure. No playground Linguagem, selecione *Resumir informações* e, em seguida, selecione o bloco **Resumir texto**.

1. Em *Amostra*, copie e cole a seguinte revisão:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selecione **Executar**. Examine a saída. Observe que o *Resumo extrativo* em *Detalhes* fornece pontuações de classificação para as frases mais importantes.   

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou.

1. Selecione os recursos, clique em **Excluir** e, em seguida, em **Sim** para confirmar. Os recursos serão excluídos.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço conferindo a [página do serviço de linguagem](https://learn.microsoft.com/azure/ai-services/language-service/overview).
