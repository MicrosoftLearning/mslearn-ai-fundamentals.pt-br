---
lab:
  title: Explorar o Tradutor de IA do Azure
---

# Explorar o Tradutor de IA do Azure

> **Observação** Para concluir este laboratório, você precisará de uma [assinatura do Azure](https://azure.microsoft.com/free?azure-portal=true) na qual tenha acesso administrativo.

A IA (Inteligência Artificial) pode ajudar a simplificar a tradução entre idiomas, ajudando a remover barreiras de comunicação entre países e culturas.

Para testar os recursos do serviço Tradutor de IA do Azure, vamos dar uma olhada nele em ação no Portal do Azure. Os mesmos princípios e funcionalidades se aplicam a soluções do mundo real, como sites ou aplicativos de telefone.

## Criar um recurso *Tradutor*

O serviço de Tradução pode ser usado por meio da criação de um recurso **Tradutor** ou de um recurso dos **serviços de IA do Azure**.

Para este exercício, crie um recurso **Tradutor** em sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e entre com sua conta Microsoft.

1. Clique no botão **&#65291;Criar um recurso** e pesquise *Tradutor*. Selecione Criar. Abrirá uma página para criar um recurso Tradutor. Defina-o com as seguintes configurações:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Região**: *escolha uma região disponível*.
    - **Nome**: *insira um nome exclusivo*.
    - **Tipo de preço**: Standard S0

1. Examine e crie o recurso e aguarde a conclusão da implantação. Em seguida, vá para o recurso implantado.

## Explorar o serviço de Tradutor 

Podemos explorar as funcionalidades do serviço Tradutor no Portal do Azure. 

1. No portal do Azure, no recurso implantado, revise a página *Visão geral*.

    ![Captura de tela da página de visão geral do recurso Tradutor.](media/use-translator/translator-azure-portal.png)

1. Na seção *Experimentar* da página Visão geral, na seção *De: Detecção automática*, digite o texto `Welcome to Azure AI Fundamentals`. Observe o JSON que aparece na correspondência na seção *Exibir solicitação*. 

1. Na seção *Exibir resposta*, exiba o JSON. Nos bastidores, uma *solicitação* foi enviada ao serviço de Tradutor. A *resposta* inclui o idioma de origem detectado com uma pontuação de confiança, uma tradução usando o alfabeto do idioma de saída e um código do idioma de saída. 

1. A demonstração na seção *Experimentar* mostra como seria se você criasse um aplicativo de tradução simples com uma interface do usuário. No caso da demonstração, assim que você digita o texto, uma solicitação é feita ao serviço Tradutor. Como você pôde fazer essa solicitação? Confira a guia *Código de Exemplo*. Nela, você verá exemplos de código em diferentes linguagens de programação que podem ser usados para fazer a solicitação. 

1. Identifique as linhas nos exemplos de código em que você precisa incluir a **Chave** e o **Ponto de Extremidade** do serviço Tradutor. Com sua chave e ponto de extremidade, você poderá enviar uma solicitação ao serviço Tradutor e receber uma resposta como a que viu na demonstração. 

1. Navegue até o menu esquerdo. Em *Gerenciamento de Recursos*, selecione *Chaves e Pontos de Extremidade*. Se você fosse criar um aplicativo, encontraria a chave e ponto de extremidade aqui. 

## Limpar

1. Exclua seu recurso quando terminar de usá-lo. 

## Saiba mais

Saiba mais sobre o que você pode fazer com esse serviço consultando a [página Tradução de Texto](https://learn.microsoft.com/en-us/azure/ai-services/translator/translator-overview).
