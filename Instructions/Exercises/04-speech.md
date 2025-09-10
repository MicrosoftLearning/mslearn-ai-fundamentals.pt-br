---
lab:
  title: Explorar a Fala no Portal da Fábrica de IA do Azure
---

# Explorar a Fala no Portal da Fábrica de IA do Azure

O serviço de **Fala de IA do Azure** transcreve fala em texto, e texto em fala audível. Você pode usar a Fala de IA para criar um aplicativo capaz de transcrever anotações de reunião ou gerar texto a partir da gravação de entrevistas.

Neste exercício, você usará a Fala de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para transcrever áudio usando as experiências de teste integradas. 

Este exercício levará aproximadamente **15** minutos.

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

1. Na página Playgrounds da Fábrica de IA do Azure, selecione **Experimentar o Playground de Fala**. O playground de Fala é uma interface do usuário que permite experimentar alguns recursos de Fala de IA do Azure.

## Explorar a conversão de fala em texto no Playground de Fala da Fábrica de IA do Azure

Vamos testar a *conversão de fala em texto* no Playground Fala da Fábrica de IA do Azure. 

1. Na página *Fala*, role para baixo e selecione **Transcrição em tempo real**.

1. Baixe **speech.zip** abrindo a URL `https://aka.ms/mslearn-speech-files` em uma nova guia do navegador. Usar a URL deve baixar automaticamente uma pasta no seu computador. 

1. Navegue até a pasta *Downloads* em seu computador e identifique a pasta baixada. Clique com o botão direito do mouse na pasta baixada. Selecione *Extrair Tudo...*. Em seguida, selecione *Extrair* para descompactar seu conteúdo. A pasta descompactada será exibida na tela. Feche a pasta descompactada. Observe que a pasta descompactada agora também está na pasta *Downloads*.    

1. No portal de Fala da Fábrica de IA do Azure, em *Carregar arquivos*, selecione **Procurar arquivos**. Navegue pela pasta descompactada. Selecione **WhatAICanDo.m4a** e **Abrir**.

    ![Procurar arquivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. O serviço de Fala transcreve e exibe o texto em tempo real. Se você tiver áudio no computador, poderá ouvir a gravação enquanto o texto estiver sendo transcrito.

1. Examine a saída. 

    >*Observação*: Para ver a saída completa, talvez seja necessário minimizar o *painel Configurar*. Para minimizar, selecione o ícone à direita do título *Configurar*.

1. Na saída, em *Texto*, você poderá ver o áudio transcrito em texto. 

Neste exercício, você experimentou os serviços de Fala de IA do Azure no Playground Fala da Fábrica de IA do Azure. Em seguida, você usou a Transcrição em tempo real para transcrever uma gravação de áudio. Você pôde ver a transcrição de texto sendo gerada à medida que o arquivo de áudio era reproduzido.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Este exercício demonstrou uma das muitas funcionalidades do serviço de Fala. Saiba mais sobre o que você pode fazer com esse serviço consultando a [página de Fala](https://azure.microsoft.com/services/cognitive-services/speech-services).
