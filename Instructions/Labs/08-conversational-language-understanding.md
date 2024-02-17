---
lab:
  title: Usar a compreensão da linguagem coloquial com o Language Studio
---

# Usar a compreensão da linguagem coloquial com o Language Studio

Cada vez mais, esperamos que os computadores sejam capazes de usar IA para reconhecer comandos em linguagem natural falados ou digitados. Por exemplo, talvez você queira que um sistema de automação residencial controle dispositivos em sua casa usando comandos de voz, como "acender a luz" ou "ligar o ventilador". Os dispositivos com tecnologia de IA podem entender esses comandos e tomar as medidas apropriadas.

Neste exercício, você usará o Language Studio para criar e testar um projeto que envia instruções para dispositivos como luzes ou ventiladores. Você usará os recursos do serviço de compreensão da linguagem coloquial para configurar seu projeto. 

## Criar um recurso de *Linguagem*

Você pode usar muitos recursos da Linguagem de IA do Azure com um recurso **Linguagem** ou **serviços de IA do Azure**. Em alguns casos, somente um recurso de idioma pode ser usado. Para o exercício abaixo, usaremos um recurso **Linguagem**. Caso ainda não tenha feito isso, crie um recurso de **Linguagem** em sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true), entrando com a conta da Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise *Serviço de linguagem*. Selecione **criar** um plano do **Serviço de Linguagem**. Você será levado para uma página para *Selecionar recursos adicionais**. Mantenha a seleção padrão e clique em **Continuar para criar seu recurso**. 

1. Na página **Criar idioma**, configure-o com as seguintes definições:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: Leste dos EUA.
    - **Nome**: *insira um nome exclusivo*.
    - **Tipo de preço**: *F0 Gratuito ou S se o F0 Gratuito não estiver disponível*
    - **Ao marcar esta caixa, reconheço que li e compreendi todos os termos abaixo**: *Selecionado*.

1. Selecione **Examinar + criar** e, em seguida, **Criar** e aguarde a conclusão da implantação.


### Criar um aplicativo de Compreensão da Linguagem Coloquial

Para implementar o reconhecimento de linguagem natural com a compreensão da linguagem coloquial, crie um aplicativo e, depois, adicione entidades, intenções e enunciados para definir os comandos que você deseja executar no aplicativo.

1. Em uma nova guia do navegador, abra o portal do Language Studio em [https://language.azure.com](https://language.azure.com?azure-portal=true) e entre usando a conta Microsoft associada à sua assinatura do Azure.

1. Se for solicitado a escolher um recurso de idioma, selecione as seguintes configurações:
    - **Diretório do Azure**: *O diretório do Azure que contém a sua assinatura*.
    - **Assinatura do Azure**: *sua assinatura do Azure*.
    - **Recurso de Linguagem**: *O recurso de Linguagem que você criou anteriormente.*

   Se você ***não*** foi solicitado a escolher um recurso de idioma, pode ser porque você tem vários recursos de idioma em sua assinatura; nesse caso:
    1. Na barra na parte superior da página, selecione **Configurações (&#9881;)**.
    2. Na página **Configurações**, exiba a guia **Recursos**.
    3. Selecione o recurso de idioma que você acabou de criar e clique em **Alternar recurso**.
    4. Na parte superior da página, clique em **Language Studio** para retornar à página inicial do Language Studio.

1. Na parte superior do portal do Language Studio, no menu **Criar**, selecione **Compreensão da linguagem coloquial**.

1. Na caixa de diálogo **Criar um projeto**, na página **Inserir informações básicas**, insira os seguintes detalhes e selecione **Avançar**:
    - **Nome**: *crie um nome exclusivo*
    - **Idioma primário dos enunciados**: *Inglês*
    - **Habilitar vários idiomas no projeto**: *não selecionar*
    - **Descrição**: `Simple home automation`

    > **Dica**: Anote o *nome do projeto*; você o usará mais tarde.

1. Na página **Análise e conclusão**, selecione **Criar**.

### Criar intenções, enunciados e entidades

Uma *intenção* é uma ação que você deseja executar, por exemplo, talvez você queira acender uma luz ou desligar um ventilador. Nesse caso, você definirá duas intenções: uma para ligar um dispositivo e outra para desligar um dispositivo. Para cada intenção, você especificará exemplos de *enunciados* que indicam o tipo de linguagem usado para indicar a intenção.

1. No painel **Definição de esquema**, verifique se a opção **Intenções** está selecionada e escolha **Adicionar**. Adicione uma intenção com o nome `switch_on` (em letras minúsculas) e selecione **Adicionar intenção**.

    ![Selecione Adicionar em Intenções no painel Criar Esquema.](media/conversational-language-understanding/build-schema.png)

    ![Adicione a intenção switch_on e selecione Adicionar intenção.](media/conversational-language-understanding/add-intent.png)

1. Selecione a intenção **switch_on**. Isso levará você para a página **Rotulagem de dados**. Na lista suspensa **Intenção**, selecione **switch_on**. Ao lado da intenção **switch_on**, digite o enunciado `turn the light on` e pressione **Enter** para enviá-lo à lista.

    ![Adicione um enunciado ao conjunto de treinamento digitando "ativar a luz" em Enunciado.](media/conversational-language-understanding/add-utterance-on.png)

1. O serviço de linguagem precisa de pelo menos cinco exemplos de enunciado diferentes para cada intenção para treinar suficientemente o modelo de linguagem. Adicione mais cinco exemplos de enunciado à intenção **switch_on**:  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

1. No painel **Rotulagem de entidades para treinamento** no lado direito da tela, selecione **Rótulos** e **Adicionar entidade**. Digite `device` (em letras minúsculas) e selecione **Listar** e **Adicionar entidade**.

    ![Adicione uma entidade selecionando Marcas no painel Marcar entidades para treinamento e depois selecione Adicionar entidade.](media/conversational-language-understanding/add-entity.png)

    ![Digite no dispositivo em Nome da entidade, selecione Lista e, depois, clique em Adicionar entidade.](media/conversational-language-understanding/add-entity-device.png)

1. No enunciado ***turn the fan on***, realce a palavra "fan". Em seguida, na lista exibida, na caixa *Pesquisar por uma entidade*, selecione **dispositivo**.

    ![Realce a palavra ventilador no enunciado e selecione dispositivo.](media/conversational-language-understanding/switch-on-entity.png)

1. Faça o mesmo em todos os enunciados. Rotule o restante dos enunciados *fan* ou *light* com a entidade **device**. Quando terminar, verifique se você tem os seguintes enunciados e selecione **Salvar alterações**:

    | **intenção** | **enunciado** | **entidade** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | Ligar o ventilador      | Dispositivo – *selecionar ventilador* |
    | switch_on   | Acender as luzes    | Dispositivo – *selecionar luzes* |
    | switch_on   | Ligar as luzes | Dispositivo – *selecionar luzes* |
    | switch_on   | Ative o ventilador     | Dispositivo – *selecionar ventilador* |
    | switch_on   | Ligar o ventilador   | Dispositivo – *selecionar ventilador* |
    | switch_on   | Ative a luz   | Dispositivo – *selecionar luzes* |

    ![Quando terminar, selecione Salvar alterações.](media/conversational-language-understanding/save-changes.png) 

1. No painel à esquerda, selecione **Definição de esquema** e verifique se a intenção **switch_on** está listada. Em seguida, selecione **Adicionar** e adicione uma nova intenção com o nome `switch_off` (em letras minúsculas).

    ![Retorne à tela Criar esquema e adicione uma intenção switch_off.](media/conversational-language-understanding/add-switch-off.png) 

1. Selecione a intenção **switch_off**. Isso levará você para a página **Rotulagem de dados**. Na lista suspensa **Intenção**, selecione **switch_off**. Ao lado da intenção **switch_off**, adicione o enunciado `turn the light off`.

1. Adicione mais cinco exemplos de enunciado à intenção **switch_off**.
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. Rotule as palavras *light* ou *fan* com a entidade **device**. Quando terminar, verifique se você tem os seguintes enunciados e selecione **Salvar alterações**:  

    | **intenção** | **enunciado** | **entidade** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | Desligar o ventilador    | Dispositivo – *selecionar ventilador* | 
    | switch_off   | Apague as luzes  | Dispositivo – *selecionar luzes* |
    | switch_off   | Desativar as luzes | Dispositivo – *selecionar luzes* |
    | switch_off   | Desligue o ventilador | Dispositivo – *selecionar ventilador* |
    | switch_off   | Desligar o ventilador | Dispositivo – *selecionar ventilador* |
    | switch_off   | Apague as luzes | Dispositivo – *selecionar luzes* |

### Treinar o modelo

Agora está tudo pronto para usar as intenções e entidades definidas para treinar o modelo de linguagem coloquial de seu aplicativo.

1. No lado esquerdo do Language Studio, selecione **Trabalhos de treinamento** e **Iniciar um trabalho de treinamento**. Use as configurações a seguir:
    - **Treinar um novo modelo**: *selecionado e escolha um nome do modelo*
    - **Modo de treinamento**: treinamento padrão (gratuito)
    - **Divisão de dados**: *selecione Dividir automaticamente o conjunto de testes com base nos dados de treinamento, manter os percentuais padrão*
    - Selecione **Treinar** na parte inferior da página.

1. Aguarde a conclusão do treinamento.

### Implantar e testar o modelo

Para usar seu modelo treinado em um aplicativo cliente, você precisa implantá-lo como um ponto de extremidade para o qual os aplicativos cliente podem enviar novos enunciados, a partir dos quais as intenções e entidades serão previstas.

1. No lado esquerdo do Language Studio, selecione **Implantando um modelo**.

1. Selecione o nome do modelo e clique em **Adicionar implantação**. Use estas configurações:
    - **Criar ou selecionar um nome de implantação existente**: *selecione Criar um nome de implantação. Adicione um nome exclusivo*.
    - **Atribuir um modelo treinado ao nome da implantação**: *selecione o nome do modelo treinado*.
    - Escolha **Implantar**

    > **Dica**: Anote o *nome da implantação*, pois você o usará mais tarde. 

1. Quando o modelo for implantado, selecione **Testando as implantações** no lado esquerdo da página e escolha o modelo implantado em **Nome da implantação**.

1. Insira o seguinte texto e selecione **Executar o teste**:

    `switch the light on`

    ![Teste o modelo selecionando o modelo implantado e depois inserindo texto e selecionando Executar o teste.](media/conversational-language-understanding/test-model.png) 

    Revise o resultado retornado, indicando que ele inclui a intenção prevista (que deve ser **switch_on**) e a entidade prevista (**dispositivo**) com pontuações de confiança que indicam a probabilidade calculada pelo modelo para a intenção e a entidade previstas. A guia JSON mostra um comparativo de confiança para cada intenção potencial (aquela com a pontuação de confiança mais alta é a intenção prevista)

1. Limpe a caixa de texto e teste o modelo com os seguintes enunciados em *Insira o texto ou carregue um documento de texto*:
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

Agora você configurou com êxito um projeto de linguagem coloquial e definiu entidades, intenções e enunciados. Você viu como treinar e implantar um modelo no Language Studio. E você experimentou com os dois enunciados definidos e alguns que você não definiu explicitamente, mas o modelo foi capaz de determinar.

> **OBSERVAÇÃO**: A compreensão da linguagem coloquial fornece a inteligência para interpretar a intenção da entrada; ela não executa nenhuma ação, como acender a luz ou ligar o ventilador. Um desenvolvedor precisaria criar um aplicativo que use o modelo de Compreensão da linguagem coloquial para determinar a intenção do usuário e automatizar a ação apropriada.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o [portal do Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou. 1. Selecione o recurso e escolha **Excluir** e, em seguida, **Sim** para confirmar. Assim, o recurso é excluído.

## Saiba mais

Esse aplicativo mostra apenas algumas das funcionalidades do recurso de Compreensão da Linguagem Coloquial do Serviço de linguagem. Saiba mais sobre o que você pode fazer com esse serviço conferindo a [página Compreensão da Linguagem Coloquial](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview).
