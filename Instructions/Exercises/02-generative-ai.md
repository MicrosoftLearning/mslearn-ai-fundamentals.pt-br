---
lab:
  title: Explorar a IA generativa no Portal da Fábrica de IA do Azure
---

# Explorar a IA generativa no Portal da Fábrica de IA do Azure

A IA generativa descreve uma categoria de recursos dentro da IA que criam conteúdos. As pessoas geralmente interagem com IA generativa incorporada a aplicativos de chat. Neste exercício, você experimentará a IA generativa no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes. 

Este exercício levará aproximadamente **20** minutos.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page do portal da Fábrica de IA do Azure.](./media/ai-foundry-portal.png)

1. Na seção **Explorar modelos e capacidades**, pesquise `gpt-4o`. Em seguida, nos resultados da pesquisa, selecione o modelo **gpt-4o** para exibir seus detalhes.

    ![Captura de tela da página de detalhes do gpt-4o.](./media/gpt-4o-details.png)

1. Selecione **Usar este modelo**.

1. No assistente **Criar projeto**, insira um nome válido para o projeto. Então, expanda **Opções avançadas** para especificar as seguintes configurações para seu projeto:
    - **Recurso da Fábrica de IA do Azure**: *Insira um nome válido para o recurso da Fábrica de IA.*
    - **Assinatura**: *sua assinatura do Azure*
    - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
    - **Região**: Selecione qualquer região **Recomendada para Fábrica de IA**\*
    
    \**As implantações de modelo são restritas por cotas regionais. Se você selecionar uma região na qual não houver cota disponível suficiente, poderá precisar escolher uma região alternativa para criar um novo recurso posteriormente.*

1. Selecione **Criar**. Aguarde até que seu projeto seja criado. Isso pode levar alguns minutos.

    Se for solicitado que você implante o modelo em uma região diferente, use as configurações padrão para fazer isso.

## Explorar a IA generativa no playground de chat da Fábrica de IA do Azure

1. Depois que o projeto tiver sido criado, no painel de tarefas à esquerda, selecione **Playgrounds**. 

    >*Dica*: Se necessário, expanda o menu para ler seu conteúdo clicando no ícone "expandir" superior.

1. Na página Playgrounds da Fábrica de IA do Azure, selecione **Experimentar o Playground Chat**. Feche as dicas ou os painéis de início rápido abertos.

    O Playground Chat é uma interface do usuário que permite que você teste a criação de um aplicativo de chat com diferentes modelos de IA generativa.

    ![Captura de tela da página de detalhes do gpt-4o.](./media/chat-playground.png)

    >*Dica*: Se você não vir o painel **Configuração** na tela do playground de chat, expanda o tamanho da janela.  

1. Para usar o Playground Chat, você precisa associá-lo a um modelo implantado. No painel **Configuração** do playground de chat, verifique se o modelo **gpt-4o** implantado anteriormente está selecionado. 

    >*Observação*: Você precisa selecionar **Aplicar alterações** sempre que fizer alterações no painel **Configuração**.

1. No painel **Configuração**, observe as instruções padrão e o contexto do modelo, que devem ser semelhantes a:

    `You are an AI assistant that helps people find information.`

    Esse tipo de instrução é comumente chamado de *prompt do sistema* e é usado para fornecer diretrizes e restrições às respostas do modelo.

1. Revise o painel *Histórico de chats*, que contém alguns prompts de exemplo para ajudá-lo a começar e uma caixa de consulta para inserir seus próprios prompts. 

1. Vamos tentar gerar uma resposta usando um prompt com um objetivo específico. Na caixa de chat, insira o seguinte prompt:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Analise a resposta. Lembre-se de que a resposta específica que você receber pode variar devido à natureza da IA generativa.

1. Vamos tentar outro prompt. Insira o seguinte:

    ```prompt
    Where's a good location in the city to stay?
    ```

1. Revise a resposta, que fornecerá alguns lugares para ficar em Paris. Observe que a sessão de chat mantém o contexto dos prompts anteriores, portanto ela sabe que “a cidade” em questão é Paris.

1. Vamos iterar com base em prompts e respostas anteriores para refinar o resultado Digite a seguinte solicitação:

    ```prompt
    Can you give me more information about dining options near the first location?
    ```

1. Revise a resposta, que fornecerá opções de alimentação perto de um local da resposta anterior. 

1. Agora, vamos fornecer uma fonte para basear a resposta em um escopo específico de informações. Insira o seguinte: 

    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Revise a resposta, que fornecerá informações com base no site fornecido. 

1. Vamos tentar adicionar contexto para maximizar a relevância da resposta. Digite a seguinte solicitação: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Revise a resposta e a argumentação da resposta.  

1. Agora, tente definir expectativas claras para a resposta. Digite a seguinte solicitação:

    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Revise a resposta, que fornecerá uma lista numerada de pontos turísticos para ver em Paris.

## Exibir o código do cliente

1. Na parte superior da página Playground de chats, selecione **Exibir código**.
1. Revise os código de exemplo, que são fornecidos para várias linguagens de programação, SDKs e opções de autenticação.

    Esses códigos de exemplo podem ajudar os desenvolvedores a começar rapidamente ao criar aplicativos cliente que interajam com seu modelo implantado.

1. Feche a janela do código de exemplo.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou.
1. Selecione **Excluir grupo de recursos** e, em seguida, **insira o nome do grupo de recursos** para confirmar. Em seguida, o grupo de recursos é excluído.
