---
lab:
  title: Explorar a Fala no Portal da Fábrica de IA do Azure
---

# Explorar a Fala no Portal da Fábrica de IA do Azure

A Fala de IA do Azure transcreve fala em texto e converte texto em fala audível. Você pode usar a Fala de IA para criar um aplicativo que transcreva notas de reuniões ou gere texto a partir de gravações de entrevistas, ou para dar suporte a um assistente de IA interativo capaz de responder a comandos e perguntas faladas.

Neste exercício, você irá usar a Fala de IA do Azure no portal da Fábrica de IA do Azure da plataforma da Microsoft para criar aplicativos inteligentes para explorar os principais recursos de Fala de IA do Azure. 

Este exercício levará aproximadamente **15** minutos.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page do portal da Fábrica de IA do Azure.](./media/ai-foundry-portal.png)

1. Role até a parte inferior da página e selecione o bloco **Explorar os serviços de IA do Azure**.

    ![Captura de tela do bloco Explorar serviços de IA do Azure.](./media/ai-services.png)

1. Na página Serviços de IA do Azure, selecione o bloco **Fala**.

    ![Captura de tela do bloco Fala.](./media/speech.png)

1. Na página **Fala**, selecione **Ir para o playground de Fala**. Então, quando solicitado, crie um novo projeto com as seguintes configurações:
    - **Nome do projeto**: *Insira um nome válido para seu projeto.*
    - **Configurações avançadas**:
        - **Assinatura**: *sua assinatura do Azure*
        - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
        - **Região**: *Selecione qualquer região **AI Foundry recommended***
        - **Fábrica de IA ou OpenAI do Azure** *Criar um novo recurso da Fábrica de IA do Azure com um nome válido*

1. Selecione **Criar**. Aguarde até que seu projeto seja criado. Isso pode levar alguns minutos.

1. Quando o projeto for criado, você será levado para um playground de **Fala** (caso não seja, no painel de tarefas à esquerda, selecione **Playgrounds** e abra o playground de Fala a partir daí.)

    O playground de Fala é uma interface do usuário que permite experimentar alguns recursos de Fala de IA do Azure.  

## Explorar a conversão de fala em texto no Playground de Fala da Fábrica de IA do Azure

Vamos testar a *conversão de fala em texto* no Playground Fala da Fábrica de IA do Azure.

1. Baixe **[speech.zip](https://aka.ms/mslearn-speech-files)** de `https://aka.ms/mslearn-speech-files` em uma nova guia no navegador. Depois de baixar o arquivo, extraia-o para uma pasta local. 

1. De volta ao portal da Fábrica de IA do Azure, na página Fala, na guia **Conversão de Fala em Texto**, selecione **Transcrição em tempo real**.

1. Em **Carregar arquivos**, selecione **Procurar arquivos** e carregue **WhatAICanDo.m4a** da pasta em que ele foi baixado e extraído.

    O serviço de Fala transcreve e exibe o texto em tempo real. Se você tiver áudio no computador, poderá ouvir a gravação enquanto o texto estiver sendo transcrito.

    ![Captura de tela da interface de transcrição em tempo real no playground de Fala.](./media/real-time-transcription.png)

1. Examine a saída. 

    >*Dica*: Para ver a saída completa, talvez seja necessário minimizar o *painel Configurar*. Para minimizar, selecione o ícone à direita do título *Configurar*.

    Na saída, em **Texto**, você poderá ver o áudio transcrito em texto.

## Explorar a conversão de texto em fala no playground de Fala da Fábrica de IA do Azure

Agora vamos ver como a Fala de IA do Azure pode gerar fala audível a partir de texto.

1. No playground de Fala, selecione a guia **Conversão de texto em fala** e verifique se **Galeria de voz** está selecionada.
1. Visualize as vozes disponíveis e selecione uma (como *Ava Multilíngue*).
1. No painel **Detalhes da voz**, selecione a guia **Experimentar**. Em seguida, insira algum texto (por exemplo, `The rain in Spain stays mainly in the plain`) e use o botão **Reproduzir** para sintetizar fala a partir do texto.

    ![Captura de tela da interface Galeria de voz no playground de Fala.](./media/voice-gallery.png)

    O texto é falado usando a voz selecionada. Você pode tentar outras vozes para comparar a saída falada.

## Limpar

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione **Excluir grupo de recursos** e, em seguida, **insira o nome do grupo de recursos** para confirmar. Em seguida, o grupo de recursos é excluído.

## Saiba mais

Este exercício demonstrou uma das muitas funcionalidades do serviço de Fala. Saiba mais sobre o que você pode fazer com esse serviço consultando a [página de Fala](https://azure.microsoft.com/services/cognitive-services/speech-services).
