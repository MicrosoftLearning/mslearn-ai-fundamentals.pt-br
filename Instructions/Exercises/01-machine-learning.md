---
lab:
  title: Explorar o Machine Learning Automatizado no Azure Machine Learning
---

# Explorar o Machine Learning Automatizado no Azure Machine Learning

Neste exercício, você usará o recurso de machine learning automatizado no Azure Machine Learning para treinar e avaliar um modelo de machine learning. Em seguida, você implantará e testará o modelo treinado.

Este exercício deve levar aproximadamente **35** minutos para ser concluído.

## Criar um workspace do Azure Machine Learning

Para usar o Azure Machine Learning, você precisa provisionar um workspace do Azure Machine Learning em sua assinatura do Azure. Em seguida, você poderá usar o Estúdio do Azure Machine Learning para trabalhar com os recursos em seu workspace.

> **Dica**: se você já tiver um workspace do Azure Machine Learning, poderá usá-lo e pular para a próxima tarefa.

1. Entre no [portal do Azure](https://portal.azure.com) em `https://portal.azure.com` usando suas credenciais da Microsoft.

1. Selecione **+ Criar um recurso**, pesquise *Machine Learning* e crie um recurso do **Azure Machine Learning** com as seguintes configurações:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *crie ou selecione um grupo de recursos*.
    - **Nome**: *insira um nome exclusivo para o seu workspace*.
    - **Região**: Leste dos EUA.
    - **Conta de armazenamento**: *anote a nova conta de armazenamento padrão que será criada para o workspace*.
    - **Cofre de chaves**: *anote o novo cofre de chaves padrão que será criado para o workspace*.
    - **Application Insights**: *anote o novo recurso Application Insights padrão que será criado para o workspace*.
    - **Registro de contêiner**: nenhum (*será criado um automaticamente quando você implantar um modelo em um contêiner pela primeira vez*).

1. Selecione **Examinar + criar**e **Criar**. Aguarde até que o workspace seja criado (isso pode demorar alguns minutos) e acesse o recurso implantado.

#### Iniciar estúdio 

1. No recurso do workspace do Azure Machine Learning, selecione **Iniciar estúdio** (ou abra uma nova guia do navegador e navegue até [https://ml.azure.com](https://ml.azure.com) e entre no estúdio do Azure Machine Learning usando sua conta da Microsoft). Feche todas as mensagens exibidas.

1. No Estúdio do Azure Machine Learning, você verá o workspace recém-criado. Caso contrário, selecione **Todos os workspaces** no menu à esquerda e selecione o workspace que você acabou de criar.

## Usar aprendizado de máquina automatizado para treinar um modelo

O aprendizado de máquina automatizado permite que você experimente vários algoritmos e parâmetros para treinar vários modelos e identificar o melhor para seus dados. Nesse caso, você usa um conjunto de dados de detalhes históricos de aluguel de bicicletas para treinar um modelo que prevê o número de aluguéis de bicicletas que deve ser esperado em um determinado dia, com base em características sazonais e meteorológicas.

> **Citação**: *os dados usados neste exercício são derivados do [Capital Bikeshare](https://www.capitalbikeshare.com/system-data) e são usados de acordo com o [contrato de licença](https://www.capitalbikeshare.com/data-license-agreement)* de dados publicado.

1. No [estúdio do Azure Machine Learning](https://ml.azure.com?azure-portal=true), veja a página **ML Automatizado** (em **Criação**).

1. Crie um novo trabalho de ML automatizado com as seguintes configurações, usando **Avançar** conforme necessário para avançar dentro da interface do usuário:

    **Configurações básicas**:

    - **Nome do trabalho**: o campo de nome do trabalho já deve estar pré-preenchido com um nome exclusivo. Mantenha como está.
    - **Nome do novo experimento**: `mslearn-bike-rental`
    - **Descrição**: `Automated machine learning for bike rental prediction`
    - **Marcas**: *nenhuma*

   **Tipo de tarefa e dados**:

    - **Selecionar tipo de tarefa**: regressão
    - **Selecionar os dados**:
        - crie um ativo de dados com as seguintes configurações:
            - **Tipo de dados**:
                - **Nome**: `bike-rentals`
                - **Descrição**: `Historic bike rental data`
                - **Tipo**: Tabela (mltable)
            - **Fonte de dados**:
                - Selecionar **Dos arquivos locais**
            - **Tipo de armazenamento de destino**:
                - **Tipo de armazenamento de dados**: Armazenamento do Blobs do Azure
                - **Nome**: workspaceblobstore
            - **Seleção de MLtable**:
                - *Baixe e descompacte a [pasta bike-data](https://aka.ms/bike-rentals) de `https://aka.ms/bike-rentals`.*
                - **Carregar pasta**: *carregue a pasta **bike-data** extraída, que contém os arquivos de definição de tabela e dados necessários para o conjunto de dados de treinamento.*
        - Selecione o ativo de dados recém-criado **bike-rentals** e continue definindo o trabalho de ML automatizado na próxima página (**Configurações da tarefa**).

    **Configurações da tarefa**:

    - **Tipo de tarefa**: regressão
    - **Conjunto de dados**: bike-rentals
    - **Coluna de destino**: aluguéis (inteiro)
    - **Definições de configuração adicionais:**
        - **Métrica primária**: NormalizedRootMeanSquaredError
        - **Explicar o melhor modelo**: *<u>Não</u>selecionado*
        - **Habilitar empilhamento de conjunto**: *<u>não</u>selecionado*
        - **Usar todos os modelos com suporte**: <u>Não</u>selecionado. *Você restringirá o trabalho para experimentar apenas alguns algoritmos específicos.*
        - **Modelos permitidos**: *selecione apenas **RandomForest** e **LightGBM**. O ideal seria tentar usar o máximo possível, mas cada modelo adicionado aumenta o tempo necessário para executar o trabalho.*
    - **Limites**: *expanda esta seção*
        - **Avaliações máximas**: `3`
        - **Máximo de avaliações simultâneas**: `3`
        - **Máximo de nós**: `3`
        - **Limite de pontuação da métrica**: `0.085` (* de modo que se um modelo atingir uma pontuação de métrica de raiz do erro quadrático médio normalizada de até 0,085, o trabalho será encerrado.*)
        - **Tempo limite de experimento**: `15`
        - **Tempo limite de iteração**: `15`
        - **Habilitar encerramento antecipado**: *selecionado*
    - **Validação e teste**:
        - **Tipo de validação**: divisão de validação de treinamento
        - **Percentual de dados de validação**: 10
        - **Conjunto de dados de teste**: nenhum

    **Computação:**

    - **Selecionar tipo de computação**: sem servidor
    - **Tipo de máquina virtual**: CPU
    - **Camada da máquina virtual**: dedicada
    - **Tamanho da máquina virtual**: Standard_DS3_V2\*
    - **Número de instâncias**: 1

    \* *Se sua assinatura restringir os tamanhos de VM disponíveis para você, escolha qualquer tamanho disponível.*

1. Envie o trabalho de treinamento. Ele é iniciado automaticamente.

1. Aguarde a conclusão do trabalho. Isso pode demorar um pouco, então agora é um bom momento para um café.

## Examinar o melhor modelo

Quando o trabalho de machine learning automatizado for concluído, você poderá examinar o melhor modelo treinado.

1. Na guia **Visão geral** do trabalho de machine learning automatizado, observe o resumo do melhor modelo.
    ![Captura de tela do resumo do melhor modelo do trabalho de machine learning automatizado com uma caixa em torno do nome do algoritmo.](./media/use-automated-machine-learning/complete-run.png)
  
1. Selecione o texto em **Nome do algoritmo** do melhor modelo para exibir os respectivos detalhes.

1. Selecione a guia **Métricas** e selecione os gráficos **residuais** e **predicted_true** se eles ainda não estiverem selecionados.

    Examine os gráficos que mostram o desempenho do modelo. O gráfico de **resíduos** mostra os *resíduos* (as diferenças entre valores previstos e reais) como um histograma. O gráfico **predicted_true** compara os valores previstos com os valores verdadeiros.

## Implantar e testar o modelo

1. Na guia **Modelo** para obter o melhor modelo treinado pelo trabalho de machine learning automatizado, selecione **Implantar** e use a opção **ponto de extremidade em tempo real** para implantar o modelo com as seguintes configurações:
    - **Máquina virtual**: Standard_DS3_v2
    - **Contagem de instâncias**: 3
    - **Ponto de extremidade**: Novo
    - **Nome do ponto de extremidade**: *Deixe o padrão ou verifique se ele é globalmente exclusivo*
    - **Nome da implantação**: *Manter o padrão*
    - **Coleta de dados de inferência**: *Disabled*
    - **Empacotar modelo**: *Disabled*

    > **Observação**: se você receber uma mensagem informando que não há cota suficiente para selecionar a máquina virtual *Standard_DS3_v2*, selecione uma diferente.

1. Aguarde até o início da implantação – isso pode levar alguns segundos. O **Status da implantação** para o ponto de extremidade será indicado na parte principal da página como *Em execução*.
1. Aguarde até que o **Status de implantação** mude para *Bem-sucedida*. Isso pode levar de 5 a 10 minutos.

## Testar o serviço implantado

Agora você pode testar o serviço implantado.

1. No Estúdio do Azure Machine Learning, no menu à esquerda, selecione **Pontos de Extremidade** e abra o ponto de extremidade em tempo real que você criou.

1. Na exibição de página do ponto de extremidade em tempo real, exiba a guia **Teste**.

1. No painel **Dados de entrada para testar o ponto de extremidade**, substitua o modelo JSON pelos seguintes dados de entrada:

    ```json
      {
     "input_data": {
       "columns": [
         "day",
         "mnth",
         "year",
         "season",
         "holiday",
         "weekday",
         "workingday",
         "weathersit",
         "temp",
         "atemp",
         "hum",
         "windspeed"
       ],
       "index": [0],
       "data": [[1,1,2022,2,0,1,1,2,0.3,0.3,0.3,0.3]]
     }
    }

    ```

1. Clique no botão**Testar**.

1. Revise os resultados do teste, que incluem um número previsto de aluguéis com base nos recursos de entrada – semelhante ao seguinte:

    ```JSON
    [
      352.3564674945718
    ]
    ```

    O painel de teste pegou os dados de entrada e usou o modelo que você treinou para retornar o número previsto de locações.

## Exibir código para consumir o serviço

Agora que você tem um ponto de extremidade de serviço preditivo, os desenvolvedores podem criar aplicativos que o consomem.

1. Na página do ponto de extremidade em tempo real, exiba a guia **Consumir**.
1. Examine o código de exemplo para consumir seu ponto de extremidade, que é fornecido para várias linguagens de programação.

Vamos revisar o que você fez. Você usou um conjunto de dados históricos de locação de bicicletas para treinar um modelo. O modelo prevê o número de locações de bicicletas esperadas em um determinado dia, com base em *recursos *sazonais e meteorológicos. Por fim, você testou o modelo e revisou o código que um desenvolvedor pode usar para criar um aplicativo para consumi-lo.

## Limpar

O serviço Web que você criou está hospedado em uma *Instância de Contêiner do Azure*. Se você não pretender experimentá-lo ainda mais, exclua o ponto de extremidade para evitar o acúmulo de uso desnecessário do Azure.

1. No [Estúdio do Azure Machine Learning](https://ml.azure.com), na guia **Pontos de Extremidade**, selecione o ponto de extremidade implantado. Depois, selecione **Excluir** e confirme que você deseja excluir o ponto de extremidade.

    Excluir sua computação garante que a assinatura não seja cobrada pelos recursos de computação. No entanto, você receberá a cobrança de uma pequena quantidade de armazenamento de dados, desde que o workspace do Azure Machine Learning exista em sua assinatura. Se tiver terminado de explorar o Azure Machine Learning, exclua o workspace do Azure Machine Learning e os recursos associados.

Para excluir seu workspace:

1. No [portal do Azure](https://portal.azure.com), na página **Grupos de recursos**, abra o grupo de recursos que você especificou ao criar seu Workspace do Azure Machine Learning.
2. Clique em **Excluir grupo de recursos**, digite o nome do grupo de recursos para confirmar que deseja excluí-lo e selecione **Excluir**.
