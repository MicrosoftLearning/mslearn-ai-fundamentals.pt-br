---
lab:
  title: Analisar imagens no Portal da Fábrica de IA do Azure
---

# Analisar imagens no Portal da Fábrica de IA do Azure

**A Visão de IA do Azure** inclui vários recursos para entender o conteúdo e o contexto da imagem e extrair informações de imagens. Neste exercício, você usará a Visão de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para analisar imagens usando as experiências de teste internas. 

Por exemplo, suponha que o varejista fictício *Northwind Traders* tenha decidido implementar uma “loja inteligente”, monitorada pelos serviços de IA para identificar os clientes que precisam de assistência e direcionar os funcionários para ajudá-los. Ao usar a Visão de IA do Azure, imagens captadas por câmeras em toda a loja podem ser analisadas para fornecer descrições significativas daquilo que elas retratam.

Este exercício levará aproximadamente **20** minutos.

## Baixar e extrair arquivos de imagem

1. Baixe **[image-analysis.zip](https://aka.ms/mslearn-images-for-analysis)** de `https://aka.ms/mslearn-images-for-analysis`.
1. Extraia o arquivo de .zip baixado para uma pasta em seu computador.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page do portal da Fábrica de IA do Azure.](./media/ai-foundry-portal.png)

1. Role até a parte inferior da página e selecione o bloco **Explorar os serviços de IA do Azure**.

    ![Captura de tela do bloco Explorar serviços de IA do Azure.](./media/ai-services.png)

1. Na página Serviços de IA do Azure, selecione o bloco **Visão + Documento**.

    ![Captura de tela do bloco Visão + Documento.](./media/vision-tile.png)

1. Na página **Visão + Documento**, exiba a guia **Imagem** e selecione o bloco **Legenda de imagem**.

    ![Captura de tela do bloco Legenda de imagem.](./media/image-captioning-tile.png)

1. No painel **Adicionar legendas a imagens**, use o botão **selecionar um hub** para **criar um novo hub** com as seguintes configurações:
    - **Nome do hub**: *Insira um nome válido para o hub.*
    - **Assinatura**: *sua assinatura do Azure*
    - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
    - **Localização**: *Selecione um dos seguintes locais**/:
        - Leste dos EUA
        - França Central
        - Coreia Central
        - Europa Ocidental
        - Oeste dos EUA
    - **Conectar os serviços de IA do Azure**: *Criar um novo recurso dos serviços de IA do Azure com um nome válido*
    - **Conectar-se à Pesquisa de IA do Azure**: Ignorar a conexão

    \**No momento em que este artigo está sendo escrito, há suporte para a Visão de IA do Azure em hubs nas seguintes regiões*.

1. Quando o hub for criado, você será solicitado a criar um projeto. Insira um nome adequado para o projeto e selecione **Criar projeto**.

## Gerar legendas para uma imagem

Vamos usar a funcionalidade de legenda de imagem da Visão de IA do Azure para analisar imagens tiradas por uma câmera na loja *Northwind Traders*. As legendas de imagem estão disponíveis por meio dos recursos **Legenda** e **Legendas Densas**.

1. No painel de tarefas à esquerda, selecione **Serviços de IA**.

    *Agora você precisa repetir as etapas usadas anteriormente para voltar à interface da legenda de imagem e usar seu novo projeto baseado no hub.*

1. Na página **Serviços de IA**, selecione o bloco **Visão + Documento**. Em seguida, na página **Visão + Documento**, na guia **Imagem**, selecione o bloco **Legenda de imagem**.

1. Na página **Adicionar legendas a imagens**, no menu de seleção de *Serviços de IA do Azure Conectados*, verifique se o recurso de serviços de IA do Azure que você criou em seu hub está selecionado.

1. Use o link **Procurar um arquivo** para carregar a imagem **store-camera-1.jpg** dos arquivos que você baixou e extraiu anteriormente.

1. Observe o texto de legenda gerado, visível no painel **Atributos detectados** à direita da imagem.

    ![Captura de tela da página Adicionar legendas a imagens com uma imagem analisada.](./media/image-captioning.png)

    A funcionalidade **Legenda** fornece uma única frase em inglês legível por humanos que descreve o conteúdo da imagem.

1. Em seguida, use a mesma imagem para executar **Legendas densas**. Retorne à página **Visão + Documento** selecionando a seta de **&larr;** *voltar* no topo da página. Em seguida, na página **Visão + Documento**, na guia **Imagem**, selecione o bloco **Legendas densas**.

    O recurso **Legendas Densas** difere da capacidade **Legenda**, pois fornece várias legendas legíveis por humanos para uma imagem, uma descrevendo o conteúdo da imagem e outras, cada uma cobrindo os objetos essenciais detectados na imagem. Cada objeto detectado inclui uma caixa delimitadora, que define as coordenadas de pixel dentro da imagem associada ao objeto.

1. Carregue a imagem **store-camera-1.jpg** novamente e visualize os resultados de legendas densas.

    ![Captura de tela dos resultados de legendas densas.](./media/dense-captioning.png)

    Passe o mouse sobre qualquer uma das legendas na lista de **Atributos detectados** e observe que uma legenda é gerada para cada objeto detectado na imagem.

## Marcar imagens 

O próximo recurso que você experimentará é a funcionalidade *Extrair Marcas*. A funcionalidade Extrair marcas é baseada em milhares de objetos reconhecíveis, incluindo seres vivos, cenários e ações.

1. Retorne à página **Visão + Documento** clicando na seta de **&larr;** *voltar* na parte superior da página. Em seguida, na página **Visão + Documento**a guia **Imagem**, selecione o bloco **Extração de marcas comuns**.
1. Carregue o arquivo **store-camera-2.jpg** da pasta extraída anteriormente.
1. Examine a lista de marcas extraídas da imagem e a pontuação de confiança para cada uma no painel de atributos detectado. Aqui, a pontuação de confiança é a probabilidade de que o texto do atributo detectado descreva o que realmente está na imagem. Observe na lista de marcas que ele inclui não apenas objetos, mas ações, como *compras*, *vendas*e *pendente*.

    ![Uma captura de tela do painel detectar atributos no Vision Studio com pontuações de texto e de confiança exibidas ao lado da imagem original.](./media/analyze-images-vision/detect-attributes.png)

## Detecção de objetos

Nessa tarefa, você usará o recurso de **Detecção de objeto** da Análise de Imagem. A detecção de objetos detecta e extrai caixas delimitadoras com base em milhares de objetos e seres vivos reconhecíveis .

1. Retorne à página **Visão + Documento** clicando na seta de **&larr;** *voltar* na parte superior da página. Em seguida, na guia **Imagem**, selecione o bloco **Detecção de objetos comuns**.

1. Carregue o arquivo **store-camera-3.jpg**.

1. Na caixa **Atributos Detectados**, observe a lista de objetos detectados e suas pontuações de confiança.

    ![Captura de tela dos resultados de legendas densas.](./media/object-detection.png)

1. Tente detectar os objetos em **store-camera-4.jpg**

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1. Abra o [portal do Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou. 
1. Selecione **Excluir grupo de recursos** e, em seguida, **insira o nome do grupo de recursos** para confirmar. Em seguida, o grupo de recursos é excluído.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço consultando a página [Visão de IA do Azure](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
