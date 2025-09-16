---
lab:
  title: Extrair dados com compreensão de conteúdo no portal da Fábrica de IA do Azure
---

# Extrair dados com compreensão de conteúdo no portal da Fábrica de IA do Azure

A **Compreensão de Conteúdo da IA do Azure** usa a IA generativa para processar o conteúdo de vários tipos (documentos, imagens, vídeos e áudio) em um formato de saída definido pelo usuário.

Neste exercício, você usa a Compreensão de Conteúdo da IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criação de aplicativos inteligentes, no reconhecimento de dados de faturas. 

Esse exercício leva aproximadamente **25** minutos.

## Criar um projeto da Fábrica de IA do Azure e uma tarefa de compreensão de conteúdo

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page da Fábrica de IA do Azure com "Criar um agente" selecionado.](./media/azure-ai-foundry-home-page.png)

1. Em uma nova janela do navegador, abra a [página de exploração de Serviços de IA do Azure](https://ai.azure.com/explore/aiservices).

1. Na página *Serviços de IA*, selecione o bloco *Experimentar a Compreensão de Conteúdo*.

1. Selecione **Selecionar ou criar um projeto para iniciar**. 

1. Selecione **+ Criar um projeto**.

1. No assistente, insira um nome válido para seu projeto. 

1. Clique em **Opções avançadas** e especifique as seguintes configurações:
    - **Recurso da Fábrica de IA do Azure**: *manter o nome padrão*
    - **Assinatura**: *sua assinatura do Azure*
    - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
    - **Região**: selecione um dos seguintes locais:
        * Oeste dos EUA
        * Suécia Central
        * Leste da Austrália

1. Selecione **Criar**. Aguarde a conclusão do processo de configuração. Isso pode levar alguns minutos.

    >**Observação**: se você receber um erro de permissões, clique no botão **Corrigir** para adicionar as permissões apropriadas para continuar.

1. Quando o projeto for criado, você será levado por padrão para a janela de criação de tarefas de compreensão de conteúdo. Use as seguintes configurações para criar uma tarefa de compreensão de conteúdo:
    - **Nome da tarefa:**: `contoso-invoice`
    - **Descrição**: `An invoice analysis task`
    - *Selecionar análise de conteúdo de arquivo único*
    - **Configurações avançadas**: *mantenha o padrão*.

1. Selecione **Criar** e aguarde a criação da tarefa. 

1. Selecione sua tarefa **contoso-invoice**. 

## Analise uma fatura com a Compreensão de Conteúdo de IA do Azure na Fábrica de IA do Azure 

Suponha que você queira extrair dados de várias faturas e colocar os dados em um banco de dados. Você pode usar a Compreensão de Conteúdo da IA do Azure para analisar uma fatura e criar seu próprio analisador, que pode analisar outras faturas semelhantes. Vamos começar definindo seu esquema.

#### Definir seu esquema 

1. Na página *Definir esquema*, você pode adicionar arquivos de teste. Baixe [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) em `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Carregue o arquivo na página de **definição do esquema**. Selecione o modelo de **extração de dados de fatura**. O modelo de extração de dados de fatura tem campos de dados pré-selecionados que o analisador tentará detectar. 

    ![Captura de tela da página de definição de esquema na ferramenta de compreensão de conteúdo.](./media/content-understanding/define-schema.png)

1. Selecione **Criar**. Agora, você tem a capacidade de modificar o esquema, adicionando ou excluindo campos. Quando terminar de revisar os campos, selecione **Salvar**.

    ![Captura da página de esquema de definição após a seleção de criação.](./media/content-understanding/define-schema-2.png)

1. Aguarde a conclusão da análise. Isso pode demorar um pouco.

#### Teste o analisador 

1. Quando a análise for concluída, você poderá ver como o analisador se saiu na página *Analisador de Teste*. Examine a guia *Campos* (*Observação*: talvez seja necessário expandir a janela para ver os resultados completos). Esses dados estão alinhados com o que você vê na fatura? 
    ![Captura de tela da página do analisador de teste com a guia de resultados de campos destacada.](./media/content-understanding/test-analyzer-fields.png)

1. Observe a *pontuação de confiança* ao lado de cada campo. A pontuação de confiança representa o quanto o modelo está confiante de que seu resultado é preciso. Resultados com pontuações de confiança mais próximos de 100% indicam mais confiança na previsão.

1. Examine a guia *Resultado*. As mesmas informações que você vê renderizadas na guia de campos estão na guia de resultados em JSON. O JSON mostra a aparência das informações quando são enviadas de e para um aplicativo cliente. 

    ![Captura de tela da página do analisador de teste com a guia de resultados destacada.](./media/content-understanding/test-analyzer-result.png)

1. O serviço de Compreensão de Conteúdo deve ter identificado corretamente o texto que corresponde aos campos no esquema. Se não tiver feito isso, você poderá usar a página *Dados do rótulo* para fazer upload de outro formulário de exemplo e identificar explicitamente o texto correto para cada campo. Quando estiver satisfeito com a capacidade do analisador de detectar os dados na fatura, selecione a guia **Lista do Analisador**. 

#### Crie o seu analisador 

Agora que você treinou um modelo para extrair campos do seu exemplo de fatura, pode criar um analisador para usar com formulários semelhantes. Ao criar um analisador, você pode implantar o modelo e usá-lo para automatizar outras tarefas de fatura.

1. Na guia *Lista do Analisador*, selecione **+ Criar Analisador**. Insira o seguinte: 
    - **Nome**: `invoice-analyzer`
    - **Descrição**: `An invoice analyzer`

    ![Captura de tela da página inicial do analisador.](./media/content-understanding/build-analyzer.png)

1. Selecione **Compilar**. Aguarde até que o novo analisador esteja pronto (use o botão Atualizar para verificar). Seu analisador usa um modelo preditivo baseado no esquema que você definiu e testou nas etapas anteriores. 
1. Agora, vamos tentar testar o analisador que você criou. Baixe uma fatura diferente da Contoso [contoso-invoice-2.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf) de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf`.
1. Retorne à página *Lista do Analisador* e clique no link invoice-analyzer. Os campos definidos no esquema do analisador serão exibidos.
1. Na página do analisador de faturas, selecione *Testar*.
1. Use o botão **+ Carregar arquivos de teste** para carregar *contoso-receipt-2.pdf*. Selecione **Executar análise** para extrair dados de campo do formulário de teste. Examine os resultados do teste.

    ![Captura de tela dos resultados do teste para o analisador que você criou.](./media/content-understanding/build-analyzer-2.png)

1. Selecione a guia *Exemplo de código*. Procure pelo *ponto de extremidade* no código. Na fase *Criar analisador* do processo, você implantou seu modelo de compreensão de conteúdo em um ponto de extremidade. O ponto de extremidade pode ser usado em código semelhante ao que você vê no exemplo para incorporar o modelo em um processo reproduzível em um aplicativo.  

    ![Captura de tela do exemplo de código para o analisador que você criou.](./media/content-understanding/code-example.png)

## Limpar

Se tiver terminado de usar o serviço Compreensão de Conteúdo, deve excluir os recursos que criou neste exercício para evitar incorrer em custos desnecessários do Azure.

- No Portal da Fábrica de IA do Azure, navegue até o projeto contoso-receipt e exclua-o.
- No portal do Azure, exclua o grupo de recursos criado para este exercício.
