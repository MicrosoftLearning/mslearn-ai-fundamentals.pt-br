---
lab:
  title: Explorar o Serviço OpenAI do Azure
---

# Explore o OpenAI do Azure

O Serviço OpenAI do Azure traz os modelos de IA generativa desenvolvidos pelo OpenAI para a plataforma do Azure, permitindo que você desenvolva soluções avançadas de IA que se beneficiem da segurança, escalabilidade e integração de serviços fornecidos pela plataforma de nuvem do Azure.

Neste exercício, você explorará o Serviço OpenAI do Azure e o usará para implantar e experimentar modelos de IA generativa.

Este exercício levará aproximadamente **25** minutos.

## Antes de começar

Você precisará de uma assinatura do Azure aprovada para acesso ao serviço OpenAI do Azure para modelos de texto e código e modelos de geração de imagem DALL-E.

- Para se inscrever em uma assinatura gratuita do Azure, visite [https://azure.microsoft.com/free](https://azure.microsoft.com/free).
- Para solicitar acesso ao serviço OpenAI do Azure, visite [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Provisionar um recurso de OpenAI do Azure

Antes de usar os modelos do OpenAI do Azure, você precisa provisionar um recurso do OpenAI do Azure em sua assinatura do Azure.

1. Faça logon no [Portal do Azure](https://portal.azure.com).
2. Crie um recurso do **OpenAI do Azure** com as seguintes configurações:
    - **Assinatura**: *Uma assinatura do Azure que foi aprovada para acesso ao serviço OpenAI do Azure.*
    - **Grupo de recursos**: *Escolha um grupo de recursos existente ou crie um novo com um nome de sua escolha.*
    - **Região**: Leste dos EUA\*
    - **Nome**: *um nome exclusivo de sua preferência*
    - **Tipo de preço**: Standard S0

    > \* Diferentes regiões têm disponibilidade e cota diferentes para modelos. Neste exercício, você usará um modelo GPT-35-Turbo para a geração de texto e um modelo DALL-E para a geração de imagem, ambos com suporte no Leste dos EUA.

3. Aguarde o fim da implantação. Em seguida, vá para o recurso OpenAI do Azure implantado no portal do Azure.

## Explorar o Estúdio do Azure OpenAI

Você pode implantar, gerenciar e explorar modelos em seu Serviço OpenAI do Azure usando o Estúdio OpenAI do Azure.

1. Na página **Visão geral** do recurso OpenAI do Azure, use o botão **Explorar** para abrir o Azure OpenAI Studio em uma nova guia do navegador. Como alternativa, navegue diretamente até o [Azure OpenAI Studio](https://oai.azure.com/).

    Quando você abre o Estúdio OpenAI do Azure pela primeira vez, ele deverá ser semelhante a isto:

    ![Captura de tela do Estúdio do OpenAI do Azure.](./media/generative-ai/ai-studio.png)

1. Visualize as páginas disponíveis no painel à esquerda. Você sempre pode retornar à página inicial na parte superior. Além disso, o Estúdio do OpenAI fornece várias páginas onde você pode:
    - Experimentar modelos em um *playground*.
    - Gerenciar implantações de modelo e dados.

## Implantar um modelo para geração de linguagem

Para experimentar a geração de linguagem natural, primeiro você deve implantar um modelo.

1. Veja os modelos disponíveis em sua instância de serviço do OpenAI do Azure na página **Modelos**.
1. Selecione qualquer um dos modelos de **gpt-35 turbo** para os quais o status **Implantável** é **Sim**e depois selecione **Implantar**:

    ![Captura de tela da página Modelos no Estúdio de IA do Azure.](./media/generative-ai/deploy-model.png)

1. Crie uma nova implantação com as seguintes configurações:
    - **Modelo**: gpt-35-turbo
    - **Versão do Modelo**: atualização automática para padrão
    - **Nome da implantação**: *Um nome exclusivo para sua implantação de modelo*
    - **Opções avançadas**
        - **Filtro de conteúdo**: Padrão
        - **Tipo de implantação**: Padrão
        - **Limite de taxa de tokens por minuto**: 5K\*
        - **Habilitar cota dinâmica**: Habilitado

    > \* Um limite de taxa de 5.000 tokens por minuto é mais do que adequado para concluir este exercício, deixando capacidade para outras pessoas que usam a mesma assinatura.

## Use o playground de *Chat* para trabalhar com o modelo

Agora que você implantou um modelo, você pode usá-lo no playground de *Chat* para gerar a saída de linguagem natural a partir de solicitações enviadas em uma interface de chat.

1. No [Azure OpenAI Studio](https://oai.azure.com/), navegue até o playground **Chat** no painel esquerdo.

    O playground de *Chat* fornece uma interface de chatbot com a qual você pode interagir com seu modelo implantado, conforme mostrado aqui:

    ![Captura de tela do playground de Chat no Estúdio de OpenAI do Azure.](./media/generative-ai/chat-playground.png)

1. No painel **Configuração**, verifique se a implantação de modelo está selecionada.
1. No painel **Assistente de configuração**, selecione o modelo de mensagem do sistema **Padrão** e visualize a mensagem do sistema que este modelo cria. A mensagem do sistema define como o modelo se comportará em sua sessão de chat.
1. Na seção **Sessão de chat**, insira a seguinte mensagem de usuário.

    ```
   What is generative AI?
    ```

1. Observe a saída retornada pelo modelo, que deve fornecer uma definição de IA generativa.
1. Insira a seguinte mensagem de usuário como uma pergunta de acompanhamento:

    ```
   What are three benefits it provides?
    ```

1. Examine a saída, observando que a sessão de chat manteve o acompanhamento da entrada e resposta anteriores para fornecer contexto (portanto, ela interpreta corretamente "ela" como se referindo à "IA generativa") e que ela fornece uma resposta adequada com base no que foi solicitado (ela deve retornar três benefícios da IA gerativa).

## Use o playground de *DALL-E* para gerar imagens

Além dos modelos de geração de linguagem, o Serviço OpenAI do Azure dá suporte ao modelo DALL-E 2 para geração de imagens.

> **Observação**: Você deve ter solicitado e recebido acesso à funcionalidade DALL-E em seu aplicativo de acesso ao serviço OpenAI do Azure para concluir esta seção do exercício.

1. No [Estúdio OpenAI do Azure](https://oai.azure.com/), navegue até o playground de **DALL-E** no painel esquerdo.
1. Digite a seguinte solicitação:

    ```
    A robot eating spaghetti
    ```

1. Selecione **Gerar** e visualize os resultados, que devem consistir de uma imagem com base na descrição fornecida no solicitação, semelhante a isso:

    ![Captura de tela do playground de DALL-E no Estúdio OpenAI do Azure.](./media/generative-ai/dall-e-playground.png)

1. Gere uma segunda imagem modificando a solicitação para:

    ```
    A robot eating spaghetti in the style of Rembrandt
    ```
1. Verifique se a nova imagem corresponde aos requisitos da solicitação, semelhante a isso:

    ![Captura de tela das imagens geradas por DALL-E no Estúdio OpenAI do Azure.](./media/generative-ai/dall-e-results.png)

## Limpeza

Quando terminar de usar o recurso OpenAI do Azure, lembre-se de excluir a implantação ou todo o recurso no [portal do Azure](https://portal.azure.com/?azure-portal=true).
