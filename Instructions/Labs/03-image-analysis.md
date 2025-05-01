---
lab:
  title: Analisar imagens no Portal da Fábrica de IA do Azure
---

# Analisar imagens no Portal da Fábrica de IA do Azure

**A Visão de IA do Azure** inclui vários recursos para entender o conteúdo e o contexto da imagem e extrair informações de imagens. Neste exercício, você usará a Visão de IA do Azure no portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, para analisar imagens usando as experiências de teste internas. 

Por exemplo, suponha que o varejista fictício *Northwind Traders* tenha decidido implementar uma “loja inteligente”, monitorada pelos serviços de IA para identificar os clientes que precisam de assistência e direcionar os funcionários para ajudá-los. Ao usar a Visão de IA do Azure, imagens captadas por câmeras em toda a loja podem ser analisadas para fornecer descrições significativas daquilo que elas retratam.

## Criar um projeto no portal do Foundry da IA do Azure

1. Em uma guia do navegador, navegue até a [Fábrica de IA do Azure](https://ai.azure.com?azure-portal=true).

1. Entre com sua conta. 

1. Na home page do portal da Fábrica de IA do Azure, selecione **Criar um projeto**. Na Fábrica de IA do Azure, os projetos são contêineres que ajudam a organizar o trabalho.  

    ![Captura de tela da home page da Fábrica de IA do Azure com "Criar um projeto" selecionado.](./media/azure-ai-foundry-home-page.png)

1. No painel *Criar um projeto*, você verá um nome de projeto gerado, que pode ser mantido como está. Caso tenha criado um hub no passado, você verá uma lista de *novos* recursos do Azure a serem criados ou uma lista suspensa de hubs existentes. Se você vir a lista suspensa de hubs existentes, selecione *Criar novo hub*, crie um nome exclusivo para seu hub e selecione *Avançar*.  
 
    ![Captura de tela do painel criar um projeto com nomes gerados automaticamente para hub e projeto.](./media/azure-ai-foundry-create-project.png)

    > **Importante**: você precisará de um recurso de serviços de IA do Azure provisionado em um local específico para concluir o restante do laboratório.

1. No mesmo painel *Criar um projeto*, selecione **Personalizar** e selecione um dos seguintes **locais**: *Leste dos EUA, França Central, Coreia Central, Oeste da Europa ou Oeste dos EUA* para concluir o restante do laboratório. Selecione **Avançar** e **Criar**. 

1. Anote os recursos criados: 
    - Serviços de IA do Azure
    - Hub de IA do Azure
    - Projeto de IA do Azure
    - Conta de armazenamento
    - Key vault
    - Grupo de recursos  
 
1. Depois que os recursos forem criados, a página *Visão geral* do projeto abrirá. No menu à esquerda da tela, selecione **Serviços de IA**.
 
    ![Captura de tela do menu à esquerda da tela do projeto com os Serviços de IA selecionados.](./media/azure-ai-foundry-ai-services.png)  

1. Na página *Serviços de IA*, clique no bloco *Visão + Documento* para experimentar os recursos Visão de IA do Azure e Documento.

    ![Captura de tela do bloco Visão e Documento selecionado na página Serviços de IA.](./media/vision-document-tile.png)

## Gerar legendas para uma imagem

Vamos usar a funcionalidade de legenda de imagem da Visão de IA do Azure para analisar imagens tiradas por uma câmera na loja *Northwind Traders*. As legendas de imagem estão disponíveis por meio dos recursos **Legenda** e **Legendas Densas**.

1. Na página *Visão + Documento*, role para baixo e selecione **Imagem** em *Exibir todos os outros recursos de visão*. Em seguida, selecione o bloco **Legenda de imagem**.

    ![Captura de tela do bloco de legenda de imagem na seção de imagem da página Visão e Documento.](./media/vision-image-captioning-tile.png)

1. Na página **Adicionar legendas a imagens**, examine o recurso ao qual você se conectou e que está listado no subtítulo **Experimentar**. Você não precisará fazer nenhuma alteração. (*Observação*: se você não personalizou um local de recurso válido anteriormente durante a criação do recurso, poderá ser solicitado que você crie um novo recurso de serviços de IA do Azure que esteja em uma região válida. Você precisará criar o novo recurso para continuar o laboratório.)  

1. Selecione [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) para baixar **image-analysis.zip.** Abra a pasta no computador e localize o arquivo chamado **store-camera-1.jpg**, que contém a seguinte imagem:

    ![Imagem de um pai usando uma câmera de celular para tirar uma foto do filho em uma loja](./media/analyze-images-vision/store-camera-1.jpg)

1. Carregue a imagem **store-camera-1.jpg** arrastando-a para a caixa **Arrastar e soltar arquivos aqui** ou navegando até ela no sistema de arquivos.

1. Observe o texto de legenda gerado, visível no painel **Atributos detectados** à direita da imagem.

    A funcionalidade **Legenda** fornece uma única frase em inglês legível por humanos que descreve o conteúdo da imagem.

1. Em seguida, use a mesma imagem para executar **Legendas densas**. Retorne à página **Visão + Documento** clicando na seta de *voltar* na parte superior da página. Na página *Visão + Documento*, selecione a guia **Imagem** e, em seguida, selecione o bloco **Legendas densas**.

    O recurso **Legendas Densas** difere da capacidade **Legenda**, pois fornece várias legendas legíveis por humanos para uma imagem, uma descrevendo o conteúdo da imagem e outras, cada uma cobrindo os objetos essenciais detectados na imagem. Cada objeto detectado inclui uma caixa delimitadora, que define as coordenadas de pixel dentro da imagem associada ao objeto.

1. Passe o mouse sobre uma das legendas na lista de atributos **Detectados** e observe o que acontece dentro da imagem.

    ![A imagem e suas legendas são exibidas.](./media/analyze-images-vision/dense-captioning.png)

    Mova o cursor do mouse sobre as outras legendas da lista e observe como a caixa delimitadora muda na imagem para realçar a parte da imagem usada para gerar a legenda.

## Marcar imagens 

O próximo recurso que você experimentará é a funcionalidade *Extrair Marcas*. A funcionalidade Extrair marcas é baseada em milhares de objetos reconhecíveis, incluindo seres vivos, cenários e ações.

1. Retorne à página *Visão + Documento* da Fábrica de IA do Azure, selecione a guia **Imagem** e selecione o bloco **Extração de marca comum**.

1. Abra a pasta que contém as imagens que você baixou e localize o arquivo chamado **store-image-2.jpg**, que tem esta aparência:

    ![Imagem de uma pessoa com uma cesta de compras em um supermercado](./media/analyze-images-vision/store-camera-2.jpg)

1. Carregue o arquivo **store-camera-2.jpg** .

1. Examine a lista de marcas extraídas da imagem e a pontuação de confiança para cada uma no painel de atributos detectado. Aqui, a pontuação de confiança é a probabilidade de que o texto do atributo detectado descreva o que realmente está na imagem. Observe na lista de marcas que ele inclui não apenas objetos, mas ações, como *compras*, *vendas*e *pendente*.

    ![Uma captura de tela do painel detectar atributos no Vision Studio com pontuações de texto e de confiança exibidas ao lado da imagem original.](./media/analyze-images-vision/detect-attributes.png)

## Detecção de objetos

Nessa tarefa, você usará o recurso de **Detecção de objeto** da Análise de Imagem. A detecção de objetos detecta e extrai caixas delimitadoras com base em milhares de objetos e seres vivos reconhecíveis .

1. Retorne à página *Visão + Documento* da Fábrica de IA do Azure, selecione a guia **Imagem** e selecione o bloco **Detecção de objeto comum**.

1. Abra a pasta que contém as imagens que você baixou e localize o arquivo chamado **store-camera-3.jpg**, que tem essa aparência:

    ![Imagem de uma pessoa com um carrinho de compras](./media/analyze-images-vision/store-camera-3.jpg)

1. Carregue o arquivo **store-camera-3.jpg**.

1. Na caixa **Atributos Detectados**, observe a lista de objetos detectados e suas pontuações de confiança.

1. Passe o cursor do mouse sobre os objetos na lista de **Atributos detectados** para realçar a caixa delimitadora do objeto na imagem.

1. Mova o controle deslizante **Valor de limite** até que um valor de 70 seja exibido à direita do controle deslizante. Observe o que acontece com os objetos na lista. O controle deslizante de limite especifica que somente objetos identificados com uma pontuação de confiança ou probabilidade maior que o limite devem ser exibidos.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita a geração de custos desnecessários.

1.  Abra o [portal do Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém os recursos que você criou. 
1.  Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço consultando a página [Visão de IA do Azure](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
