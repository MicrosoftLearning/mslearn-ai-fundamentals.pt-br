---
lab:
  title: Explorar a IA generativa no Portal da Fábrica de IA do Azure
---

# Explorar a IA generativa no Portal da Fábrica de IA do Azure

A IA generativa descreve uma categoria de recursos dentro da IA que criam conteúdos. As pessoas normalmente interagem com a IA generativa que foi incorporada a aplicativos de chat. Neste exercício, você experimentará a IA generativa no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes. 

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

## Explorar a IA generativa no playground de chat da Fábrica de IA do Azure

1. Na página Playgrounds da Fábrica de IA do Azure, selecione **Experimentar o Playground Chat**. O Playground Chat é uma interface do usuário que permite que você teste a criação de um aplicativo de chat com diferentes modelos de IA generativa.  

1. Para usar o Playground Chat, você precisa associá-lo a um modelo implantado. No playground do Chat, o **gpt-4o** precisa estar selecionado. Se você não vir nenhuma implantação, será necessário selecionar **+ Criar uma implantação**, buscar **gpt-4o**, clicar em **Confirmar** e, por fim, em **Implantar**.

1. No playground chat, você pode usar o modelo implantado quando ele aparecer no menu de seleção *Implantação*. É importante ressaltar que você precisa selecionar **Aplicar alterações** depois de fazer alterações na *Configuração*. 

1. Considere as seguintes maneiras de melhorar as respostas de um assistente de IA generativa:
    - Comece com uma meta específica para o que deseja que o assitente faça
    - Itere com base em prompts e respostas anteriores para refinar o resultado
    - Forneça uma fonte para basear a resposta em um escopo específico de informações
    - Adicione contexto para maximizar a adequação e a relevância da resposta
    - Defina expectativas claras para a resposta

1. Vamos tentar gerar uma resposta usando um prompt com um objetivo específico. Na caixa de chat, insira o seguinte prompt:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Revise a resposta. **Observação**: tenha em mente que a resposta específica recebida pode variar devido à natureza da IA generativa.
 
1. Vamos tentar outro prompt. Insira o seguinte:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Revise a resposta, que fornecerá alguns lugares para ficar em Paris.

1. Vamos iterar com base em prompts e respostas anteriores para refinar o resultado Digite o seguinte prompt:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Revise a resposta, que fornecerá opções de alimentação perto de um local da resposta anterior. 

1. Agora, vamos fornecer uma fonte para basear a resposta em um escopo específico de informações. Insira o seguinte: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Revise a resposta, que fornecerá informações com base no site fornecido. 

1. Vamos tentar adicionar contexto para maximizar a relevância da resposta. Digite o seguinte prompt: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Revise a resposta e a argumentação da resposta.  

1. Agora, tente definir expectativas claras para a resposta. Digite o seguinte prompt:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Revise a resposta, que fornecerá uma lista numerada de pontos turísticos para ver em Paris.

1. Quando terminar, você pode fechar a janela do navegador.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou.

1. Selecione os recursos, clique em **Excluir** e, em seguida, em **Sim** para confirmar. Os recursos serão excluídos.
