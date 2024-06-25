---
lab:
  title: Ler texto no Vision Studio
---

# Ler texto no Vision Studio

Neste exercício, você usará o serviço de IA do Azure para explorar as funcionalidades de reconhecimento óptico de caracteres da Visão de IA do Azure. Você usará o Vision Studio para experimentar a extração de texto de imagens, sem precisar escrever nenhum código.

Um desafio comum da pesquisa visual computacional é detectar e interpretar o texto inserido em uma imagem. Isso é conhecido no OCR (reconhecimento óptico de caracteres). Neste exercício, você usará o recurso serviços de IA do Azure, que inclui os serviços da Visão de IA do Azure. Em seguida, você usará o Vision Studio para experimentar o OCR com diferentes tipos de imagens.

## Criar um recurso dos *serviços de IA do Azure*

Você pode usar os recursos do OCR da Visão de IA do Azure com um recurso de vários serviços do **serviços de IA do Azure**. Caso ainda não tenha feito isso, crie um recurso dos **serviços de IA do Azure** em sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e entre com a conta Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise por *serviços de IA do Azure*. Selecione **criar** um plano dos **serviços de IA do Azure**. Você será levado para uma página para criar um recurso dos serviços de IA do Azure. Defina-o com as seguintes configurações:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: *Selecione a região geográfica mais próxima. Se estiver no leste dos EUA, use “Leste dos EUA 2”*.
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

1. Feche a página de configurações selecionando o “x” na parte superior da tela.

## Extrair texto de imagens no Vision Studio
    
1. Em um navegador da Web, navegue até o **Vision Studio** em [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Na página de aterrissagem **Introdução à Visão**, selecione **Reconhecimento óptico de caracteres** e, em seguida, o bloco **Extrair texto de imagens**.

1. No subtítulo **Experimentar**, confirme a política de uso do recurso lendo e marcando a caixa.  

1. Selecione [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images) para baixar **ocr-images.zip**. Em seguida, abra a pasta.

1. No portal, selecione **Procurar um arquivo** e navegue até a pasta no computador em que você baixou **ocr-images.zip**. Selecione **advert.jpg** e selecione **Abrir**.

1. Agora, examine o que é retornado:
    - Em **Atributos detectados**, qualquer texto encontrado na imagem é organizado em uma estrutura hierárquica de regiões, linhas e palavras.
    - Na imagem, o local do texto é indicado por uma caixa delimitadora, conforme mostrado aqui:

    ![Uma imagem do texto na imagem contornada.](media/read-text-computer-vision/advert-bounding-boxes.jpg)

1. Agora você pode experimentar com outra imagem. Selecione **Procurar um arquivo** e navegue até a pasta em que você salvou os arquivos do GitHub. Selecione **letter.jpg**.

    ![Uma imagem de uma carta digitada.](media/read-text-computer-vision/letter.jpg)

1. Examine os resultados da segunda imagem. Eles devem retornar o texto e as caixas delimitadoras do texto. Se você tiver tempo, experimente **note.jpg** e **receipt.jpg**.

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o **portal do Azure** em [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Para saber mais sobre o que você pode fazer com esse serviço, consulte a documentação da Visão de IA do Azure sobre [reconhecimento óptico de caracteres](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr).
