---
lab:
  title: Explorar a Fala no Portal da Fábrica de IA do Azure
---

# Explorar a Fala no Portal da Fábrica de IA do Azure

O serviço de **Fala de IA do Azure** transcreve fala em texto, e texto em fala audível. Você pode usar a Fala de IA para criar um aplicativo capaz de transcrever anotações de reunião ou gerar texto a partir da gravação de entrevistas.

Neste exercício, você usará a Fala de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para transcrever áudio usando as experiências de teste integradas. 

## Criar um projeto no portal do Foundry da IA do Azure

1. Em uma guia do navegador, navegue até a [Fábrica de IA do Azure](https://ai.azure.com?azure-portal=true).

1. Entre com sua conta. 

1. Na home page do portal da Fábrica de IA do Azure, selecione **Criar um projeto**. Na Fábrica de IA do Azure, os projetos são contêineres que ajudam a organizar o trabalho.  

    ![Captura de tela da home page da Fábrica de IA do Azure com "Criar um projeto" selecionado.](./media/azure-ai-foundry-home-page.png)

1. No painel *Criar um projeto*, você verá um nome de projeto gerado, que pode ser mantido como está. Caso tenha criado um hub no passado, você verá uma lista de *novos* recursos do Azure a serem criados ou uma lista suspensa de hubs existentes. Se você vir a lista suspensa de hubs existentes, selecione *Criar novo hub*, crie um nome exclusivo para seu hub e selecione *Avançar*.  
 
    ![Captura de tela do painel criar um projeto com nomes gerados automaticamente para hub e projeto.](./media/azure-ai-foundry-create-project.png)

> **Importante**: você precisará de um recurso de serviços de IA do Azure provisionado em um local específico para concluir o restante do laboratório.

1. No mesmo painel *Criar um projeto*, selecione **Personalizar** e selecione um dos seguintes **locais**: Leste dos EUA, França Central, Coreia Central, Oeste da Europa ou Oeste dos EUA para concluir o restante do laboratório. Em seguida, selecione **Criar**. 

1. Anote os recursos criados: 
- Serviços de IA do Azure
- Hub de IA do Azure
- Projeto de IA do Azure
- Conta de armazenamento
- Key vault
- Grupo de recursos  
 
1. Depois que os recursos forem criados, a página *Visão geral* do projeto abrirá. No menu à esquerda da tela, selecione **Serviços de IA**.
 
    ![Captura de tela do menu à esquerda da tela do projeto com os Serviços de IA selecionados.](./media/azure-ai-foundry-ai-services.png)  

1. Na página *Serviços de IA*, selecione o bloco *Fala* para experimentar os recursos de Fala de IA do Azure.

    ![Captura de tela do bloco Fala selecionado na página Serviços de IA.](./media/speech-tile.png)

## Explorar a conversão de fala em texto no Playground de Fala da Fábrica de IA do Azure

Vamos experimentar a *conversão de fala em texto* em tempo real no Playground Fala da Fábrica de IA do Azure. 

1. Na página *Fala*, role para baixo e selecione **Conversão de fala em texto em tempo real** em *Experimente funcionalidades de Fala*. O *Playground Fala* abrirá. 

1. Selecione [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) para baixar **speech.zip**. Abra a pasta . 

1. Em *Carregar arquivos*, selecione **Procurar arquivos** e navegue até a pasta em que você salvou o arquivo. Selecione **WhatAICanDo.m4a** e **Abrir**.

    ![Procurar arquivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. O serviço de Fala transcreve e exibe o texto em tempo real. Se você tiver áudio no computador, poderá ouvir a gravação enquanto o texto estiver sendo transcrito.

1. Examine a saída, que deve ter reconhecido o áudio e o transcrito com êxito em texto.

Neste exercício, você experimentou os serviços de Fala de IA do Azure no Playground Fala da Fábrica de IA do Azure. Em seguida, você usou o serviço de Conversão de fala em texto em tempo real para transcrever uma gravação de áudio. Você pôde ver a transcrição de texto sendo gerada à medida que o arquivo de áudio era reproduzido.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Este exercício demonstrou apenas algumas das funcionalidades do serviço de Fala. Saiba mais sobre o que você pode fazer com esse serviço consultando a [página de Fala](https://azure.microsoft.com/services/cognitive-services/speech-services).
