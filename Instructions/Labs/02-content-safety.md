---
lab:
  title: Explore os serviços de IA do Azure
---

# Explore os serviços de IA do Azure

Os serviços de IA do Azure ajudam os usuários a criar aplicativos de IA com APIs e modelos prontos para uso, predefinidos e personalizáveis. Neste exercício, você criará um recurso no portal do Azure e experimentará os serviços de IA do Azure. A meta deste exercício é obter uma noção geral de como os serviços de IA do Azure são provisionados e usados.

## Criar um recurso de *serviços de IA do Azure* no portal do Azure

1. Em uma guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e entre usando a conta Microsoft associada à sua assinatura do Azure.

1. Clique no botão **&#65291;Criar um recurso** e pesquise por *serviços de IA do Azure*. Selecione **criar** um plano dos **serviços de IA do Azure**. Você será levado para uma página para criar um recurso dos serviços de IA do Azure. Defina-o com as seguintes configurações:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: *Selecione a região geográfica mais próxima. Se estiver no leste dos EUA, use “Leste dos EUA 2”*.
    - **Nome**: *insira um nome exclusivo*.
    - **Tipo de preço**: *Standard S0.*
    - **Ao marcar essa caixa, confirmo que li e compreendi todos os termos abaixo**: *Selecionado*.

1. Selecione **Revisar + criar** e, em seguida, **Criar** e aguarde a conclusão da implantação.

    *Parabéns! Você acabou de criar ou provisionar um recurso dos serviços de IA do Azure. O que você provisionou em específico é um recurso de vários serviços.*

1. Após a conclusão da implantação, selecione *Ir para o recurso*. 

## Confira as chaves e o ponto de extremidade

Para incorporar os serviços de IA do Azure em aplicativos, os desenvolvedores precisam de uma chave de serviço e um ponto de extremidade. As chaves e o ponto de extremidade usados para o desenvolvimento de aplicativos podem ser encontrados no portal do Azure. 

1. No portal do Azure, selecione seu recurso. No menu à esquerda, procure em *Gerenciamento de recursos* por *Chaves e pontos de extremidade*. Selecione **Chaves e pontos de extremidade** para exibir o ponto de extremidade e as chaves do recurso. 

## Confira os serviços de IA do Azure em ação

1. Em uma guia do navegador, navegue até a [Fábrica de IA do Azure](https://ai.azure.com?azure-portal=true).

1. Entre com sua conta. 

1. Em *Trabalhar fora de um projeto*, selecione o bloco **Exibir Serviços de IA **.
 
    ![Captura de tela do menu à esquerda da tela do projeto com os Serviços de IA selecionados.](./media/view-ai-foundry-outside-project.png)  

1. Na página *Serviços de IA*, clique no bloco *Visão + Documento* para experimentar os recursos Visão de IA do Azure e Documento.

    ![Captura de tela do bloco Visão e Documento selecionado na página Serviços de IA.](./media/vision-document-tile.png)

1. Em *Exibir todos os recursos de Visão*, selecione a guia **Detecção facial**. 

1. Selecione o bloco de demonstração *Detectar rostos em uma imagem*. 

1. Experimente a detecção facial, que é um dos muitos serviços de IA do Azure. Clique em uma imagem e confira os atributos detectados. 

    ![Captura de tela da demonstração de detecção de rostos no Portal da Fábrica de IA do Azure.](./media/detect-faces-demo.png)

1. Role para baixo até a seção **Executar o código**. Selecione **Visualizar código**. Role até a seção que começa com *import os*. No código de exemplo fornecido, você verá espaços reservados onde você pode colocar uma chave e um ponto de extremidade.

    ![Captura de tela da tela de exibição de código com uma exibição dos espaços reservados de código para chave e ponto de extremidade.](./media/view-code-example.png) 

1. Se você fosse criar um aplicativo que usasse os serviços de IA do Azure, poderia começar com o código fornecido. Ao substituir os espaços reservados pela chave e pelo ponto de extremidade do seu próprio serviço, seu aplicativo poderá enviar solicitações e receber respostas que utilizam os serviços de IA do Azure. No caso da detecção facial, a *solicitação* é para que a detecção facial analise a imagem. A *resposta* são os atributos detectados. 

    >**Observação** você não precisa saber programação para concluir nenhum dos exercícios deste curso. Continuaremos a dar uma olhada nos serviços de IA do Azure em ação por meio do Portal da Fábrica de IA do Azure.  
 
## Limpar 

Depois de terminar, você pode excluir o recurso de Serviços de IA do Azure no Portal do Azure. Excluir o recurso é uma maneira de reduzir os custos acumulados quando o recurso existe na assinatura. Para fazer isso, navegue até a página **Visão geral** do recurso Serviços de IA do Azure. Selecione **Excluir** na parte superior da tela.









