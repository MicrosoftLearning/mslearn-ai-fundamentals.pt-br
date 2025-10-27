---
lab:
  title: Explorar o machine learning automatizado
---

# Explorar o machine learning automatizado

Neste exercício, você usará machine learning automatizado para treinar e avaliar um modelo de machine learning. Em seguida, você implantará e testará o modelo treinado.

> **Observação**: Este exercício foi projetado para guiar você pelas etapas para treinar e testar um modelo usando o***Azure Machine Learning***. Se você tiver uma assinatura do Azure com permissões suficientes, poderá provisionar um workspace do Azure Machine Learning e usá-lo para o exercício. No entanto, o Azure Machine Learning foi projetado para soluções de machine learning em escala empresarial que envolvem grandes volumes de dados e computação baseada em nuvem. Algumas operações no Azure Machine Learning exigem o provisionamento de computação, o que pode levar um tempo considerável. Se você não tiver acesso ao Azure ou se tiver tempo limitado para concluir o exercício, o aplicativo***ML Lab*** no navegador que inclui a funcionalidade principal do Azure ML usado neste exercício também será fornecido e você poderá usá-lo para treinar e testar modelos reais de machine learning, assim como faria no Azure ML. Embora a interface do usuário no ML Lab não seja*idêntica* ao Azure Machine Learning, é semelhante o suficiente para tornar a transição para o Azure Machine Learning intuitiva. Observe que o aplicativo ML Lab é executado no navegador, portanto, se a página for atualizada a qualquer momento, o aplicativo será reiniciado!

Este exercício deve levar aproximadamente**35** minutos para ser concluído (exceto se você usar o aplicativo ML Lab no navegador).

## Criar um workspace

Um workspace é usado para manter todos os recursos de machine learning juntos, facilitando o gerenciamento de dados, código, modelos e outros ativos em um único lugar.

1. Abra o portal para o ambiente que você deseja usar neste laboratório e entre, se solicitado:
    - [Azure Machine Learning Studio](https://ml.azure.com){:target="_blank"} no Azure em`https://ml.azure.com`
    - [ML Lab](https://aka.ms/ml-lab){:target="_blank"} no navegador em`https://aka.ms/ml-lab`

    > **Dica**: Se o Estúdio do Azure Machine Learning for aberto em um workspace existente, navegue até a página**Todos os workspaces**.

1. Crie um novo workspace com um nome adequado.

    Se você estiver usando o Azure Machine Learning, não precisará de um*Hub* para este exercício. Escolha as configurações avançadas apropriadas com base em quaisquer restrições de política em sua assinatura do Azure.

1. Depois que o workspace for criado, selecione-o para exibir sua**Página Inicial**.

    Observe que o workspace tem várias páginas, que são exibidas no painel de navegação à esquerda. Você pode expandir e recolher esse painel usando o menu **&#9776;** na parte superior.

## Baixar dados

Neste exercício, você usará um conjunto de dados de vendas de sorvetes para treinar um modelo que prevê a demanda por sorvetes em um determinado dia, com base em recursos sazonais e meteorológicos.

1. Em uma nova guia do navegador, baixe**[ml-data.zip](https://aka.ms/mslearn-ml-data)** de`https://aka.ms/mslearn-ml-data` para o computador local.
1. Extraia o arquivo**ml-data.zip** baixado para ver os arquivos que ele contém. Observe que um desses arquivos é**ice-cream.csv**, que contém os dados de vendas de sorvete necessários para este exercício.

## Usar aprendizado de máquina automatizado para treinar um modelo

O aprendizado de máquina automatizado permite que você experimente vários algoritmos e parâmetros para treinar vários modelos e identificar o melhor para seus dados.

1. No portal, exiba a página**ML automatizado** (em**Criação**).

1. Crie um novo trabalho de ML automatizado com as seguintes configurações, usando**Avançar** conforme necessário para avançar dentro da interface do usuário:

    > **Dica**: Se nenhuma informação explícita para uma configuração for fornecida nas etapas abaixo, use o valor padrão.

    **Configurações básicas**:

    - Atribua um**nome de trabalho** exclusivo para seu trabalho de machine learning automatizado

   **Tipo de tarefa e dados**:

    - Defina o tipo de tarefa como**Regressão**.
    - Criar um novo ativo de dados***tabular*** chamado**ice-cream**
        - Carregue o arquivo**ice-cream.csv** local no armazenamento do workspace padrão.
        - Inclua<u>apenas</u> as seguintes colunas (a*Data* é exclusiva para cada linha e adiciona a capacidade preditiva por conta própria):
            - **DayOfWeek**
            - **Mês**
            - **Temperatura**
            - **Rainfall**
            - **IceCreamsSold**
        - Crie o ativo de dados.
    - Verifique se o ativo de dados**ice-cream** recém-criado está selecionado antes de passar para a próxima etapa

    > **Observação**: Se você estiver usando uma assinatura do Azure para a qual não é administrador, o acesso ao armazenamento baseado em chave pode ter sido desabilitado pela política. Nesse caso, você precisará trabalhar com o administrador para permitir o acesso baseado em chave ou reconfigurar seu workspace do Azure Machine Learning para usar a autenticação do Entra ID para acessar o armazenamento. Se não puder fazer isso, use o aplicativo***ML Lab*** no navegador para este exercício.

    **Configurações da tarefa**:

    - Defina a**coluna de destino** (o rótulo que queremos que o modelo preveja) como**IceCreamsSold**.
    - Defina a**Configuração adicional**:
        - Defina a**Métrica primária** como a métrica que você deseja usar para avaliar o desempenho do modelo. Neste exercício, use a pontuação*R<sup>2</sup>*.
        - Selecione os algoritmos de modelo que você deseja experimentar (ou deixe todos selecionados)
    - Defina as**Configurações de engenharia de recursos**:
        - Use essas configurações para personalizar a engenharia de recursos (como os recursos de dados são preparados para treinamento de modelo)
    - Defina os**Limites**:
        - Use os limites para encerrar o trabalho de treinamento antecipadamente com base em critérios específicos. Neste exercício, defina os seguintes limites:
            - **Limite de pontuação da métrica**: 0,9
            - **Tempo limite do experimento (minutos)**: 15
        
        > **Observação** É importante definir esses limites ao usar o Azure Machine Learning, pois a execução de trabalhos de treinamento para todos os algoritmos possíveis e combinações de recursos pode levar horas!

    **Computação:**

    - Usar**Computação sem servidor**

    **Revisão**

    - Examine as configurações e verifique-as cuidadosamente. Em seguida, envie o trabalho de treinamento. Ele é iniciado automaticamente.

1. Aguarde a conclusão do trabalho.

    > **Dica**: Se você estiver usando o Azure Machine Learning, pode demorar um pouco. Agora pode ser um bom momento para uma pausa para o café!

## Examinar o melhor modelo

Quando o trabalho de machine learning automatizado for concluído, você poderá examinar o melhor modelo treinado.

1. Na guia**Visão geral** da página de detalhes do trabalho, exiba as informações sobre o trabalho e anote o melhor resumo do modelo.
  
1. Selecione o**Nome do algoritmo** para o melhor modelo exibir os detalhes dele. Em seguida, na página de detalhes do trabalho filho, exiba as seguintes guias:
    - **Visão geral**: Detalhes gerais do trabalho filho.
    - **Modelo**: Informações sobre o modelo treinado.
    - **Métricas** Métricas de avaliação e visualizações para o modelo com base nos dados de teste usados durante o processo de treinamento.
    - **Saídas e logs**: Informações registradas durante o processo de treinamento.

## Implantar e testar o modelo

1. Na guia**Modelo** para o melhor modelo treinado pelo trabalho de machine learning automatizado, selecione**Implantar** para implantar o modelo em um ponto de extremidade em tempo real.

    Selecione as opções de**Instâncias** e**Máquinas virtuais** apropriadas para a computação na qual o ponto de extremidade implantado será executado (que pode depender da cota disponível em sua assinatura do Azure) e atribua nomes de**ponto de extremidade** e**implantação** adequados.

1. Aguarde uma notificação informando que a implantação foi concluída.

    > **Dica**: No Estúdio do Azure Machine Learning, a implantação de ponto de extremidade pode levar de 5 a 10 minutos.

## Testar o serviço implantado

Agora você pode testar o serviço implantado.

1. No menu de navegação, selecione a página**Pontos de Extremidade** e abra o ponto de extremidade em tempo real que você criou.

1. Na página do ponto de extremidade, exiba a guia**Teste**.

1. No painel**Dados de entrada para testar o ponto de extremidade**, substitua o modelo JSON pelos seguintes dados de entrada:

    ```json
   {
     "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
   }
    ```

1. Clique no botão**Testar**.

1. Revise os resultados do teste, que incluem um número previsto de aluguéis com base nos recursos de entrada – semelhante ao seguinte:

    ```JSON
   [
       120.16208168753236
   ]
    ```

    O painel de teste pegou os dados de entrada e usou o modelo que você treinou para retornar o número previsto de locações.

## Exibir código para consumir o modelo

Agora que você tem um modelo preditivo, os desenvolvedores podem compilar aplicativos que o consomem.

1. Na página do ponto de extremidade em tempo real, exiba a guia**Consumir**.
1. Examine o código de exemplo para consumir seu modelo.

## Se o tempo permitir

Se você quiser experimentar ainda mais o machine learning automatizado, tente treinar um modelo de**classificação** com base no arquivo**penguins.csv** incluído no arquivo**ml-data.zip** baixado anteriormente. Use todas as colunas neste conjunto de dados.

Depois de treinar e implantar um modelo de classificação, você pode testá-lo no ponto de extremidade com o seguinte JSON:

```json
{
    "input_data": {
    "columns": [
        "CulmenLength",
        "CulmenDepth",
        "FlipperLength",
        "BodyMass"
    ],
    "index": [0],
    "data": [[45.2,13.8,215,4750]]
    }
}
```

## Limpar

Se você usou o Azure Machine Learning para concluir este exercício, deverá excluir os recursos criados para evitar o acúmulo de uso desnecessário do Azure.

1. No[Estúdio do Azure Machine Learning](https://ml.azure.com), na guia**Pontos de Extremidade**, selecione o ponto de extremidade implantado. Depois, selecione**Excluir** e confirme que você deseja excluir o ponto de extremidade.

    Excluir sua computação garante que a assinatura não seja cobrada pelos recursos de computação. No entanto, você receberá a cobrança de uma pequena quantidade de armazenamento de dados, desde que o workspace do Azure Machine Learning exista em sua assinatura. Se tiver terminado de explorar o Azure Machine Learning, exclua o workspace do Azure Machine Learning e os recursos associados.

Para excluir seu workspace:

1. No[portal do Azure](https://portal.azure.com), na página**Grupos de recursos**, abra o grupo de recursos que você especificou ao criar seu Workspace do Azure Machine Learning.
2. Clique em**Excluir grupo de recursos**, digite o nome do grupo de recursos para confirmar que deseja excluí-lo e selecione**Excluir**.
