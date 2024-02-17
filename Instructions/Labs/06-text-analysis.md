---
lab:
  title: Analisar texto com o Estúdio de Idiomas
---

# Analisar texto com o Estúdio de Idiomas

Neste exercício, você explorará as funcionalidades da Linguagem de IA do Azure analisando alguns exemplos de avaliações de hotéis. Você usará o Estúdio de Idiomas para entender se as avaliações são, em sua maioria, positivas ou negativas.

O Processamento de Linguagem Natural (NLP) é uma ramificação da IA que lida com a linguagem escrita e falada. Você pode usar o NLP para criar soluções que extraiam o significado semântico do texto ou da fala, ou que formulem respostas significativas em linguagem natural.

Por exemplo, suponha que a agência de viagens fictícia Margie's Travel incentive os clientes a enviar avaliações de estadias em hotéis. Você pode usar o Serviço de linguagem para identificar frases-chave, determinar quais revisões são positivas e quais são negativas ou analisar o texto da avaliação em busca de menções a entidades conhecidas, como locais ou pessoas.

O Serviço de Linguagem de IA do Azure inclui funcionalidades de análise de texto e PNL. Isso inclui a identificação de frases-chave no texto e a classificação do texto com base no sentimento.

## Criar um recurso de *Linguagem*

Você pode usar muitos recursos da Linguagem de IA do Azure com um recurso **Linguagem** ou **serviços de IA do Azure**. Em alguns casos, somente um recurso de idioma pode ser usado. Para o exercício abaixo, usaremos um recurso **Linguagem**. Caso ainda não tenha feito isso, crie um recurso de **Linguagem** em sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true), entrando com a conta da Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise *Serviço de linguagem*. Selecione **criar** um plano **Serviço de linguagem**. Você será levado a uma página para **Selecionar recursos adicionais**. Mantenha a seleção padrão e clique em **Continuar para criar seu recurso**. 

1. Na página **Criar idioma**, configure-o com as seguintes definições:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: Leste dos EUA.
    - **Nome**: *insira um nome exclusivo*.
    - **Tipo de preço**: *F0 Gratuito ou S se o F0 Gratuito não estiver disponível*
    - **Ao marcar esta caixa, reconheço que li e compreendi todos os termos abaixo**: *Selecionado*.

1. Selecione **Revisar + criar** e, em seguida, **Criar** e aguarde a conclusão da implantação.

## Configure seu recurso no Estúdio de Linguagem de IA do Azure

1. Em outra guia do navegador, abra o **Estúdio de Idiomas** em [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true) e entre.

1. Quando for solicitado **Selecionar um recurso do Azure**, faça as seguintes configurações:
    - **Diretório do Azure**: *Diretório padrão, o diretório que você está usando*
    - **Assinatura do Azure**: *Selecione a assinatura que está usando*
    - **Tipo de recurso**: linguagem
    - **Nome do recurso**: *selecione o recurso de Serviço de Linguagem que você acabou de criar*

Em seguida, selecione **Concluído**.

> **Importante**: Desde julho de 2023, os serviços de IA do Azure abrangem tudo o que era conhecido anteriormente como Serviços Cognitivos e Serviços de IA Aplicada do Azure. Algumas interfaces de usuário ainda estão atualizando sua referência de `Cognitive Services` para `Azure AI services`. Os dois nomes se referem ao mesmo tipo de recurso.

> **Observação**: Se você ***não*** foi solicitado a escolher um recurso de idioma, pode ser porque você tem vários recursos de idioma em sua assinatura; nesse caso:
> 1. Na barra na parte superior da página, selecione **Configurações (&#9881;)**. 
> 1. Na página **Configurações**, exiba a guia **Recursos**.
> 1. Selecione o recurso que acabou de criar e selecione **Alternar recurso**. Certifique-se de que a identidade gerenciada esteja **Habilitada**.
> ![Habilitar o recurso de idioma.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. Na parte superior da página, clique em **Language Studio** para retornar à página inicial do Language Studio.

## Analisar as avaliações no Estúdio de Idiomas

1. Em um navegador da Web, navegue até **Estúdio de Idiomas** em [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true).

1. Na página de aterrissagem **Bem-vindo(a) ao Estúdio de Idiomas**, selecione a guia **Classificar texto** e, em seguida, selecione o bloco **Analisar sentimentos e extrair opiniões**.

1. Em *Selecionar o idioma do texto*, selecione **Inglês**.

1. Em *Selecione seu recurso do Azure*, selecione seu recurso.

1. Em *Insira seu próprio texto, carregue um arquivo ou use um de nossos exemplos de texto*, copie e cole a seguinte avaliação:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Marque a caixa para reconhecer que a demonstração incorrerá em uso e poderá ter custos e, em seguida, selecione **Executar**.

1. Examine a saída. Observe que o *documento* é analisado quanto ao sentimento, bem como cada *sentença*. Selecione a **Sentença 1** para mostrar a análise de sentimento dessa sentença. 

Observe que há um sentimento geral seguido de pontuações próximas a três categorias: *pontuação positiva*, *pontuação neutra*, *pontuação negativa*. Em cada uma das categorias, é fornecida uma pontuação entre 0 e 1. Essas pontuações de confiança indicam a probabilidade de o texto fornecido ser um sentimento específico. 

Selecione a **Sentença 1** novamente para fechar.

1. Role a tela para cima para selecionar **Limpar caixa de texto** e copie e cole a seguinte revisão:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. Selecione **Executar**. Analise a saída, o sentimento e o nível de confiança.

1. Selecione novamente a caixa **Limpar texto** e copie e cole a revisão a seguir:

    >Muito barulhento e com quartos minúsculos Lombard Hotel, São Francisco, EUA 05/09/2018 O hotel fica localizado na Rua Lombard, que é uma estrada de SEIS pistas muito movimentada, bem na saída da Ponte Golden Gate. Tem trânsito desde o início da manhã até o fim da noite, especialmente nos finais de semana. O barulho não seria tão ruim se os quartos fossem mais isolados, mas não eram. Tive que colocar algodão nos ouvidos para conseguir dormir e fiquei cansado demais para aproveitar a cidade no dia seguinte. Os quartos são MINÚSCULOS. Eu escolhi o quarto porque tinha duas camas queen, mas elas mal cabiam ali. Com uma família de quatro pessoas no quarto, ficou bem apertado. Dito isso, os quartos são limpos, e notamos um empenho em remodelá-los. O hotel fica no distrito de Marina, com vários bons lugares para comer e a uma curta caminhada até o Presidio. Pode ser um bom hotel para jovens adultos que ficam acordados até tarde e que têm um orçamento limitado.

1. Selecione **Executar** e analise o sentimento junto com o nível de confiança. Dê uma olhada no texto e compare-o com a análise de sentimento que o serviço retornou.

Neste exercício, você usou o Estúdio de Idiomas para criar um novo recurso de idioma ou usar um recurso de idioma existente. Você ativou o recurso em Configurações antes de experimentar o serviço de mineração de sentimentos e opiniões. Em seguida, você testou o serviço com três textos.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço conferindo a [página do serviço de linguagem](https://learn.microsoft.com/azure/ai-services/language-service/overview).
