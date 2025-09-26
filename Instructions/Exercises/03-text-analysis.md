---
lab:
  title: Analisar texto no portal da Fábrica de IA do Azure
---

# Analisar texto no portal da Fábrica de IA do Azure

A Linguagem de IA do Azure inclui Análise de Texto, com recursos como reconhecimento de entidade, extração de frases-chave, resumo e análise de sentimento. Por exemplo, suponha que a agência de viagens fictícia Margie's Travel incentive os clientes a enviar avaliações de estadias em hotéis. Você pode usar o Serviço de linguagem para extrair entidades nomeadas, identificar frases-chave, resumir texto e muito mais.

Neste exercício, você usará a Linguagem de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para analisar avaliações de hotéis. 

Este exercício levará aproximadamente **20** minutos.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page do portal da Fábrica de IA do Azure.](./media/ai-foundry-portal.png)

1. Role até a parte inferior da página e selecione o bloco **Explorar os serviços de IA do Azure**.

    ![Captura de tela do bloco Explorar serviços de IA do Azure.](./media/ai-services.png)

1. Na página Serviços de IA do Azure, selecione o bloco **Idioma + Tradução**.

    ![Captura de tela do bloco Idioma + Tradução.](./media/language-tile.png)

1. Na página **Idioma + Tradução**, selecione **Experimentar o playground de idiomas**. Então, quando solicitado, crie um novo projeto com as seguintes configurações:
    - **Nome do projeto**: *Insira um nome válido para seu projeto.*
    - **Configurações avançadas**:
        - **Assinatura**: *sua assinatura do Azure*
        - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
        - **Região**: *Selecione qualquer região **AI Foundry recommended***
        - **Fábrica de IA ou OpenAI do Azure** *Criar um novo recurso da Fábrica de IA do Azure com um nome válido*

1. Selecione **Criar**. Aguarde até que seu projeto seja criado. Isso pode levar alguns minutos.

1. Quando o projeto for criado, você será levado para um playground de **Idiomas** (caso não seja, no painel de tarefas à esquerda, selecione **Playgrounds** e abra o playground de idiomas a partir daí.)

    O playground de linguagem é uma interface do usuário que permite experimentar alguns recursos da Linguagem de IA do Azure.  

## Usar a Linguagem de IA do Azure para analisar texto

A Linguagem de IA do Azure oferece uma ampla gama de recursos de análise de texto.

### Extrair entidades nomeadas com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure

*Entidades nomeadas* são palavras que descrevem pessoas, lugares e objetos com nomes próprios. Vamos usar a funcionalidade de extração de entidade nomeada da Linguagem de IA do Azure para identificar tipos de informações em uma revisão.

1. No Playground Linguagem, selecione **Extrair informações**. Em seguida, selecione o bloco **Extrair entidades nomeadas**. 

1. Em *Exemplo*, insira a seguinte revisão:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selecione **Executar**. Examine a saída.

    ![Captura de tela da interface Extrair entidades nomeadas no playground de idiomas.](./media/entity-extraction.png)

    Observe na seção *Detalhes* como as entidades extraídas vêm com informações adicionais, como pontuações de tipo e confiança. A pontuação de confiança representa a probabilidade de o tipo identificado realmente pertencer a essa categoria.

### Extrair frases-chave com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure

As *frases-chave* são as informações mais importantes no texto. Vamos usar a funcionalidade de extração de frases-chave da Linguagem de IA do Azure para extrair informações importantes de uma revisão.

1. No Playground Linguagem, selecione **Extrair informações**. Em seguida, selecione o bloco **Extrair frases-chave**. 

1. Em *Exemplo*, insira a seguinte revisão:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selecione **Executar**. Examine a saída.

    ![Captura de tela da interface Extrair frases-chave no playground de idiomas.](./media/key-phrases.png)

    Observe as diferentes frases extraídas na seção *Detalhes*. Essas frases contribuirão mais para o significado do texto.

### Resumir texto com a Linguagem de IA do Azure no portal da Fábrica de IA do Azure
 
Vejamos as funcionalidades de resumo da Linguagem de IA do Azure.

1. No playground Linguagem, selecione **Resumir informações** e, em seguida, selecione o bloco **Resumir texto**.

1. Em *Exemplo*, insira a seguinte revisão:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selecione **Executar**. Examine a saída.

    ![Captura de tela da interface Resumir texto no playground de idiomas.](./media/summarize-text.png)

    Observe que o *Resumo extrativo* em *Detalhes* fornece pontuações de classificação para as frases mais importantes.

### Analisar o sentimento no texto

A análise de sentimento é uma tarefa comum ao analisar textos, como avaliações de hotéis.

1. No playground de idiomas, selecione **Classificar texto**. Em seguida, selecione o bloco **Analisar sentimento**.

1. Em *Exemplo*, insira a seguinte revisão:
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. Selecione **Executar**. Examine a saída.

    ![Captura de tela da interface de Análise de sentimento no playground de idiomas.](./media/sentiment-analysis.png)

    Observe que a análise gera uma pontuação geral de sentimento e pontuações individuais para cada frase.

## Detectar idioma e traduzir texto

A Linguagem de IA do Azure permite detectar o idioma no qual o texto está escrito. Além disso, o Tradutor de IA do Azure permite que você traduza facilmente o texto de um idioma para outro.

### Detectar o idioma

Vamos começar detectando o idioma em que uma avaliação foi escrita.

1. No painel **Classificar Texto**, selecione o bloco **Detectar idioma**.

1. Em *Exemplo*, insira a seguinte revisão:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Selecione **Executar**. Examine a saída.

    ![Captura de tela da interface Detectar idioma no playground de idiomas.](./media/detect-language.png)

    Observe que o idioma é detectado como francês. 

### Traduzir o texto

Agora vamos traduzir a avaliação em francês para o inglês.

1. Na parte superior da página, use o link (voltar) **&larr;** ao lado do título da página **Playground de idiomas** para visualizar todos os playgrounds disponíveis.
1. Na lista de playgrounds, abra o **Playground de tradução**.
1. No Playground de tradução, selecione **Tradução de texto**.
1. No painel **Configurar**, selecione as seguintes opções de idioma:
    - **Traduzir do**: Francês
    - **Traduzir para**: Inglês
1. Em *Exemplo*, insira a avaliação em francês:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Selecione **Traduzir**. Examine a saída.

    ![Captura de tela da interface Tradução de texto no Playground de tradução.](./media/text-translation.png)

    Observe que a avaliação em francês é traduzida para o inglês.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou.
1. Selecione **Excluir grupo de recursos** e, em seguida, **insira o nome do grupo de recursos** para confirmar. Em seguida, o grupo de recursos é excluído.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço conferindo a [página do serviço de linguagem](https://learn.microsoft.com/azure/ai-services/language-service/overview).
