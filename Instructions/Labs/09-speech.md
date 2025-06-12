---
lab:
  title: Explorar a Fala no Portal da Fábrica de IA do Azure
---

# Explorar a Fala no Portal da Fábrica de IA do Azure

O serviço de **Fala de IA do Azure** transcreve fala em texto, e texto em fala audível. Você pode usar a Fala de IA para criar um aplicativo capaz de transcrever anotações de reunião ou gerar texto a partir da gravação de entrevistas.

Neste exercício, você usará a Fala de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para transcrever áudio usando as experiências de teste integradas. 

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar. 

1. No navegador, navegue até `https://ai.azure.com/managementCenter/allResources` e clique em **Criar**. Em seguida, escolha a opção para criar um novo *recurso da Fábrica de IA do Azure*.

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

    Aguarde a criação do projeto e do hub.

1. Quando o projeto for criado, a página *Visão geral* dos detalhes do projeto abrirá.
 
1. No menu à esquerda da tela, selecione **Playgrounds**.

1. Na página *Playgrounds*, selecione o bloco **Playground de Fala** para testar algumas funcionalidades da Fala de IA do Azure.

## Explorar a conversão de fala em texto no Playground de Fala da Fábrica de IA do Azure

Vamos testar a *conversão de fala em texto* no Playground Fala da Fábrica de IA do Azure. 

1. Na página *Fala*, role para baixo e selecione **Transcrição em tempo real** em *Experimentar recursos de Fala*. O *Playground Fala* abrirá. 

1. Selecione [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) para baixar **speech.zip**. Abra a pasta . 

1. Em *Carregar arquivos*, selecione **Procurar arquivos** e navegue até a pasta em que você salvou o arquivo. Selecione **WhatAICanDo.m4a** e **Abrir**.

    ![Procurar arquivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. O serviço de Fala transcreve e exibe o texto em tempo real. Se você tiver áudio no computador, poderá ouvir a gravação enquanto o texto estiver sendo transcrito.

1. Examine a saída, que deve ter reconhecido o áudio e o transcrito com êxito em texto.

Neste exercício, você experimentou os serviços de Fala de IA do Azure no Playground Fala da Fábrica de IA do Azure. Em seguida, você usou a Transcrição em tempo real para transcrever uma gravação de áudio. Você pôde ver a transcrição de texto sendo gerada à medida que o arquivo de áudio era reproduzido.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Este exercício demonstrou uma das muitas funcionalidades do serviço de Fala. Saiba mais sobre o que você pode fazer com esse serviço consultando a [página de Fala](https://azure.microsoft.com/services/cognitive-services/speech-services).
