---
lab:
  title: Detectar rostos no Vision Studio
---

# Detectar rostos no Vision Studio

As soluções do Vision geralmente exigem que a IA seja capaz de detectar rostos humanos. Suponha que a empresa de varejo Northwind Traders queira localizar onde os clientes estão em uma loja para melhor ajudá-los. Uma maneira de fazer isso é determinar se há rostos nas imagens e, se for o caso, retornar as coordenadas da caixa delimitadora ao redor dos rostos.

Para testar os recursos de detecção facial do serviço de Detecção Facial da IA do Azure, você usará o [Azure Vision Studio](https://portal.vision.cognitive.azure.com/). Essa é uma plataforma baseada em interface do usuário que permite explorar os recursos da Visão de IA do Azure sem a necessidade de escrever nenhum código.

## Criar um recurso dos *serviços de IA do Azure*

Você pode usar o serviço de Detecção Facial de IA do Azure com um recurso de vários **serviços IA do Azure**. Caso ainda não tenha feito isso, crie um recurso dos **serviços de IA do Azure** em sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true), entrando com a conta Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise por *serviços de IA do Azure*. Selecione **criar** um plano dos **serviços de IA do Azure**. Você será levado para uma página para criar um recurso dos serviços de IA do Azure. Defina-o com as seguintes configurações:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: Leste dos EUA.
    - **Nome**: *insira um nome exclusivo*.
    - **Tipo de preço**: *Standard S0.*
    - **Ao marcar essa caixa, confirmo que li e compreendi todos os termos abaixo**: *Selecionado*.

1. Selecione **Examinar + criar** e, em seguida, **Criar** e aguarde a conclusão da implantação.

## Conectar seu recurso do serviço de IA do Azure ao Vision Studio

Em seguida, conecte o recurso dos serviços de IA do Azure que você provisionou acima ao Vision Studio.

1. Em outra guia do navegador, navegue até **Vision Studio** em [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Entre com sua conta e verifique se você está usando o mesmo diretório que aquele em que criou o recurso dos serviços de IA do Azure.

1. Na página inicial do Vision Studio, selecione **Exibir todos os recursos** no título **Introdução ao Vision**.

    ![O link Exibir todos os recursos é realçado em Introdução à Visão no Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. Na página **Selecionar um recurso para trabalhar**, passe o cursor do mouse sobre o recurso criado acima na lista e marque a caixa à esquerda do nome do recurso e selecione **Selecionar como recurso padrão**.

    > **Observação**: Se o recurso não foi listado, talvez seja necessário **Atualizar** a página.

    ![A caixa de diálogo Selecionar um recurso para trabalhar é exibida com o recurso dos Serviços Cognitivos cog-ms-learn-vision-SUFFIX realçado e verificado. O botão Selecionar como recurso padrão está realçado.](./media/analyze-images-vision/default-resource.png)

1. Feche a página de configurações selecionando o "x" na parte superior direita da tela.

## Detectar rostos no Vision Studio 

1. Em um navegador da Web, navegue até o **Vision Studio** em [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Na página de aterrissagem **Introdução ao Serviço Cognitivo do Azure para Visão**, selecione a guia **Detecção Facial** e, em seguida, selecione o bloco **Detectar Rostos em uma imagem**.

1. No subtítulo **Experimentar**, confirme a política de uso do recurso lendo e marcando a caixa.  

1. Selecione cada uma das imagens de exemplo e observe os dados de detecção facial retornados.

1. Agora vamos tentar com algumas de nossas próprias imagens. Selecione [**https://aka.ms/mslearn-detect-faces**](https://aka.ms/mslearn-detect-faces) para baixar **detect-faces.zip.** Em seguida, abra a pasta no computador.

1. Localize o arquivo chamado **store-camera-1.jpg**; que contém a seguinte imagem:

    ![Uma imagem de pessoas em uma loja.](./media/create-face-solutions/store-camera-1.jpg)

1. Carregue **store-camera-1.jpg** e examine os detalhes de detecção facial retornados.

1. Localize o arquivo chamado **store-camera-2.jpg**; que contém a seguinte imagem:

    ![Uma imagem de mais pessoas em uma loja.](./media/create-face-solutions/store-camera-2.jpg)

1. Carregue **store-camera-2.jpg** e examine os detalhes de detecção facial retornados.

1. Localize o arquivo chamado **store-camera-3.jpg**; que contém a seguinte imagem:

    ![Uma imagem de pessoas em uma loja com uma planta ocultando um rosto.](./media/create-face-solutions/store-camera-3.jpg)

1. Carregue **store-camera-2.jpg** e examine os detalhes de detecção facial retornados. Observe como a Detecção Facial de IA do Azure pode detectar rostos parcialmente obscurecidos. 

Neste exercício, você explorou como os serviços de IA do Azure podem detectar rostos em imagens. Se você tiver tempo, fique à vontade para experimentar as imagens de exemplo ou algumas de suas próprias imagens.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço consultando a [página do serviço de Detecção Facial da IA do Azure](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity).
