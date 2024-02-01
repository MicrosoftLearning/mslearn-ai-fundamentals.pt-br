---
lab:
  title: Usar Respostas às Perguntas com o Language Studio
---

# Usar o modelo de Respostas às Perguntas com o Language Studio

Nesse exercício, você usará o Language Studio para criar e treinar uma base de dados de conhecimento de perguntas e respostas que serão usadas por um bot de serviços ao cliente. O conteúdo da base de dados de conhecimento virá de uma página de perguntas frequentes existente do site da Margie's Travel, uma agência de viagens fictícia. Em seguida, você usará o Language Studio para ver como ele funcionaria quando usado pelos clientes.

Ao implementar um bot, a primeira etapa é criar uma base de dados de conhecimento de pares de perguntas e respostas. Isso é usado junto com recursos internos de processamento de linguagem natural para que o bot possa interpretar perguntas e encontrar a resposta mais apropriada para o usuário.

A Linguagem de IA do Azure inclui recursos de *resposta às perguntas*, que você usará para criar uma base de dados de conhecimento. As bases de dados de conhecimento podem ser criadas inserindo pares de perguntas e respostas manualmente ou de um documento ou página da Web existente. A Margie's Travel quer usar seu documento de perguntas frequentes existente.

O recurso de respostas às perguntas personalizadas do serviço de Linguagem permite a criação rápida de uma base de dados de conhecimento, por meio da inserção de pares de pergunta e resposta ou de um documento ou página da Web existente. Em seguida, ele pode usar alguns recursos de processamento de linguagem natural integrados para interpretar perguntas e encontrar as respostas certas.

## Criar um recurso de *Linguagem*

Para usar a resposta às perguntas, você precisa de um recurso de **Linguagem**.

1. Em outra guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true), entrando com a conta Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise *Serviços Cognitivos*. Selecione **criar** um plano de **serviço de Linguagem** . Você será levado para uma página para **Selecionar recursos adicionais**. Use as configurações a seguir:
    - **Selecione os Recursos Adicionais**:
        - **Recursos padrão**: *mantenha os recursos padrão*.
        - **Recursos personalizados**: *selecione a opção respostas às perguntas personalizadas*.
     - Selecione **Continuar para criar seu recurso**
    ![Criando um recurso do Serviço de Linguagem com respostas a perguntas personalizadas habilitadas.](media/create-a-bot/create-language-service-resource.png)

1. Na página **Criar linguagem**, especifique as seguintes configurações:
    - **Detalhes do projeto**
        - **Assinatura**: *sua assinatura do Azure*.
        - **Grupo de recursos**: *selecione um grupo de recursos existente ou crie um novo*.
    - **Detalhes da Instância**
        - **Região**: *Selecionar uma região*      
        - **Nome**: *um nome exclusivo para o recurso de Linguagem*.
        - **Tipo de preço**: S (mil chamadas por minuto)
    - **Respostas às perguntas personalizadas**
        - **Localização do Azure Search**: *qualquer localização disponível*.
        - **Nível de preço do Azure Search**: F Gratuito (3 Índices) – (*Se esse nível não estiver disponível, selecione Básico*)
    - **Aviso de IA Responsável**
        - **Ao marcar esta caixa, declaro que analisei e confirmo os termos do Aviso de IA responsável**: *selecionada*.

1. Selecione **Examinar e Criar** e, em seguida, selecione **Criar**. Aguarde a implantação do serviço de Linguagem que dará suporte à sua base de dados de conhecimento de respostas às perguntas personalizadas.

    > **Observação**: caso já tenha provisionado um recurso do **Azure Cognitive Search** de camada gratuita, talvez a cota não permita a criação de outro. Nesse caso, selecione uma camada diferente de **Free F**.

## Crie um novo projeto

1. Em uma nova guia do navegador, abra o portal do Language Studio em [https://language.azure.com](https://language.azure.com?azure-portal=true) e entre usando a conta Microsoft associada à sua assinatura do Azure.
1. Se for solicitado a escolher um recurso de idioma, selecione as seguintes configurações:
    - **Diretório do Azure**: *O diretório do Azure que contém a sua assinatura*.
    - **Assinatura do Azure**: *sua assinatura do Azure*.
    - **Recurso de Linguagem**: *O recurso de Linguagem que você criou anteriormente*.

    Se você ***não*** foi solicitado a escolher um recurso de idioma, pode ser porque você tem vários recursos de idioma em sua assinatura; nesse caso:
    1. Na barra na parte superior da página, selecione **Configurações (&#9881;)**.      
    1. Na página **Configurações**, exiba a guia **Recursos**.
    1. Selecione o recurso de idioma que você acabou de criar e clique em **Alternar recurso**.
    1. Na parte superior da página, clique em **Language Studio** para retornar à página inicial do Language Studio.

1. Na parte superior do portal do Language Studio, no menu **Criar**, selecione **Respostas às perguntas personalizadas**.

    ![Respostas às perguntas personalizadas](media/create-a-bot/create-custom-question-answering.png)

1. Na página **Escolher configuração de idioma para o *recurso***, selecione **Quero selecionar o idioma quando criar um projeto neste recurso** e clique em **Avançar**.
  ![Quero selecionar a linguagem](media/create-a-bot/create-project.png)

1. Na página **Inserir informações básicas**, insira os seguintes detalhes e clique em **Avançar**:
    - **Recurso de idioma**: *escolha o seu recurso de idioma*.  
    - **Recurso de pesquisa do Azure**: *escolha o recurso de pesquisa do Azure*.
    - **Nome**: `MargiesTravel`
    - **Descrição**: `A simple knowledge base`
    - **Idioma de origem**: inglês
    - **Resposta padrão quando nenhuma resposta é retornada**: `No answer found`
1. Na página **Revisar e concluir**, selecione **Criar projeto**.
1. Você será levado à página **Gerenciar origens**. Clique em **&#65291;Adicionar origem** e selecione **URLs**.
1. **Na caixa Adicionar URLs**, selecione **+ Adicionar URL**. Digite o seguinte e selecione **Adicionar tudo**:
    - **Nome da URL**: `MargiesKB`
    - **URL**: `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/natural-language/margies_faq.docx`
    - **Classificar estrutura de arquivo**: *Detectar automaticamente*
1. Selecione **Adicionar tudo.**  

 ![Adicionar URL](media/create-a-bot/add-url.png)

## Editar a base de dados de conhecimento

Sua base de dados de conhecimento se baseia nos detalhes contidos no documento de perguntas frequentes e em algumas respostas pré-definidas. Você pode adicionar pares personalizados de perguntas e respostas para complementá-los.

1. Expanda o painel esquerdo e selecione **Editar base de dados de conhecimento**. Em seguida, selecione **+** para adicionar um novo par de perguntas.
1. Na caixa de diálogo **Adicionar um novo par de respostas e perguntas**, no **tipo de **Pergunta`Hello` e no **tipo de **Resposta`Hi`, selecione **Concluído**.
1. Expanda **Perguntas alternativas** e selecione **+ Adicionar pergunta alternativa**. Em seguida, insira `Hiya`como uma frase alternativa para "Olá".
1. Na parte superior do painel **Pares de perguntas e respostas**, selecione **Salvar** para salvar sua base de dados de conhecimento.

## Treinar e testar a base de dados de conhecimento

Agora que você tem uma base de dados de conhecimento, pode testá-la.

1. Na parte superior do painel **Pares de perguntas e respostas**, selecione **Testar** para testar sua base de dados de conhecimento.
1. No painel de teste, na parte inferior, insira a mensagem `Hi`. A resposta *Oi* deve ser retornada.
1. No painel de teste, na parte inferior, insira a mensagem `I want to book a flight`. Uma resposta apropriada das perguntas frequentes deve retornar.

    > **Observação** A resposta inclui uma *resposta curta*, bem como uma *passagem de resposta* mais detalhada. A passagem de resposta mostra o texto completo no documento de perguntas frequentes da pergunta com a correspondência mais próxima, enquanto a resposta curta é extraída da passagem de maneira inteligente. Você pode controlar se quer mostrar a resposta curta usando a caixa de seleção **Exibir resposta curta** na parte superior do painel de teste.

1. Tente outra pergunta, como `How can I cancel a reservation?`
1. Quando terminar de testar a base de dados de conhecimento, clique em **Testar** para fechar o painel de teste.

## Criar um bot para a base de dados de conhecimento

A base de dados de conhecimento fornece um serviço de back-end que os aplicativos cliente podem usar para responder a perguntas por meio de algum tipo de interface do usuário. Normalmente, esses aplicativos cliente são bots. Para disponibilizar a base de dados de conhecimento a um bot, você deve publicá-la como um serviço que possa ser acessado por HTTP. Então, você pode usar o Serviço de Bot do Azure para criar e hospedar um bot que usa a base de dados de conhecimento para responder a perguntas do usuário.

1. No painel esquerdo, selecione **Implantar base de dados de conhecimento**.
1. Na parte superior da página, selecione **Implantar**. Uma caixa de diálogo perguntará se você deseja implantar o projeto. Selecione **Implantar**.

 ![Implantar base de dados de conhecimento.](media/create-a-bot/deploy-knowledge-base.png)

1. Após a implantação do serviço, clique em **Criar um bot**. Isso abre o portal do Azure em uma nova guia do navegador para que você possa criar um Bot de Aplicativo Web em sua assinatura do Azure.
1. No portal do Azure, crie um **Bot de Aplicativo Web**. (Você pode ver uma mensagem de aviso para marcar que a origem do modelo é confiável. Você não precisa tomar nenhuma ação para essa mensagem.) Continue atualizando as seguintes configurações:

    - **Detalhes do projeto**
        - **Assinatura**: *sua assinatura do Azure*
        - **Grupo de recursos**: *o grupo de recursos que contém seu recurso de Linguagem*
    - **Detalhes da instância**
        - **Localização do grupo de recursos**: *o mesmo local do serviço de linguagem*.
    - **Bot do Azure**
        - **Identificador do bot**: *insira um nome exclusivo para o bot*(*preenchido previamente*)
    - **Escolha o tipo de preço**
        - **Tipo de preço**: Gratuito (F0) (Talvez seja necessário selecionar *Alterar plano*)
    - **ID do Aplicativo da Microsoft**
        - **Tipo de criação**: *Selecione** Criar uma nova identidade gerenciada atribuída pelo usuário*** 

5. Selecione **Avançar** para continuar atualizando as configurações. 
    - **Serviço de Aplicativo**
        - **Nome do aplicativo**: *o mesmo que a **Alça do bot** com **.azurewebsites.net** anexado automaticamente*
        - **Linguagem do SDK**: *escolha C# ou Node.js*
    - **Plano do Serviço de Aplicativo**
        - **Tipo de Criação**: *Selecione**Criar novo plano de serviço de aplicativo***
    - **Configurações do aplicativo**
        - **Chave de Recurso de Linguagem**: *você precisará copiar sua chave de recurso de linguagem e colá-la aqui*:
            - Em outra guia do navegador, acesse o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true).
            - Navegue até o recurso de serviço de linguagem.
            - Na página **Chaves e Ponto de Extremidade**, copie uma das chaves
            - Cole-a aqui.
        - **Nome do projeto de linguagem**: MargiesTravel
        - **Nome do host do ponto de extremidade do serviço de linguagem**: *preenchido previamente com o ponto de extremidade do serviço de idioma*
    - **Detalhes do serviço de linguagem**
        - **ID da assinatura**: *preenchido previamente com sua ID de assinatura*
        - **Nome do Grupo de Recursos**: *preenchido previamente com o nome do grupo de recursos*
        - **Nome da conta**: *preenchido previamente com o nome do recurso*

1. Selecione **Criar**. Aguarde enquanto o bot é criado (o ícone de notificação do canto superior direito, parecido com um sino, ficará animado enquanto você espera). Em seguida, na notificação que diz que a implantação foi concluída, clique em **Ir para o recurso** (ou, na página inicial, selecione **Grupos de recursos**, abra o grupo de recursos em que você criou o bot e selecione o recurso **Bot do Azure**.)
1. No painel à esquerda do bot, procure **Configurações**, clique em **Testar no Webchat** e aguarde até que o bot exiba a mensagem **Olá e bem-vindo(a)** (a inicialização pode demorar alguns segundos).
1. Use a interface de chat de teste para garantir que o bot responda às perguntas da sua base de dados de conhecimento conforme o esperado. Por exemplo, tente enviar `I need to cancel my hotel`.

Faça experimentos com o bot. Provavelmente, você verá que ele pode responder a perguntas frequentes com bastante precisão, mas terá capacidade limitada de interpretar perguntas para as quais não foi treinado. Use, a qualquer momento, o Language Studio para editar a base de dados de conhecimento a fim de aprimorá-la e, depois, publique-a novamente.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos que você não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou. 
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

- Para saber mais sobre o serviço de Respostas às Perguntas, confira [a documentação](https://docs.microsoft.com/azure/cognitive-services/language-service/question-answering/overview).
- Para saber mais sobre o Serviço de Bot da Microsoft, veja [a página do Serviço de Bot do Azure](https://azure.microsoft.com/services/bot-service/).
