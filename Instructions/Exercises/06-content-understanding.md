---
lab:
  title: Extrair dados com compreensão de conteúdo no portal da Fábrica de IA do Azure
---

# Extrair dados com compreensão de conteúdo no portal da Fábrica de IA do Azure

A Compreensão de Conteúdo da IA do Azure oferece análise multimodal de documentos, arquivos de áudio, vídeo e imagens para extrair informações.

Neste exercício, você irá usar a Compreensão de Conteúdo da IA do Azure no portal da Fábrica de IA do Azure da plataforma da Microsoft para criar aplicativos inteligentes para extrair informações de faturas. 

Esse exercício leva aproximadamente **25** minutos.

## Criar um projeto da Fábrica de IA do Azure para compreensão de conteúdo

1. Em um navegador da Web, abra o [Portal da Fábrica de IA do Azure](https://ai.azure.com) em `https://ai.azure.com` e entre usando suas credenciais do Azure. Feche todas as dicas ou painéis de início rápido abertos na primeira vez que você entrar e, se necessário, use o logotipo da **Fábrica de IA do Azure** no canto superior esquerdo para navegar até a home page, que é semelhante à imagem a seguir (feche o painel **Ajuda** se estiver aberto):

    ![Captura de tela da home page do portal da Fábrica de IA do Azure.](./media/ai-foundry-portal.png)

1. Role até a parte inferior da página e selecione o bloco **Explorar os serviços de IA do Azure**.

    ![Captura de tela do bloco Explorar serviços de IA do Azure.](./media/ai-services.png)

1. Na página Serviços de IA do Azure, selecione **Experimentar a Compreensão de Conteúdo**.

    ![Captura de tela do botão Experimentar a Compreensão de Conteúdo.](./media/try-content-understanding.png)

1. Na página Compreensão de Conteúdo, selecione **Criar um projeto para iniciar**. Em seguida, na caixa de diálogo **Criar projeto**, selecione o tipo de recurso recomendado (**Recurso da Fábrica de IA do Azure**):

    ![Captura de tela dos resultados da análise.](./media/resource-type.png)

1. Na **próxima** página, insira um nome válido para seu projeto. Em seguida, selecione **Opções avançadas** e especifique as seguintes configurações:
    - **Recurso da Fábrica de IA do Azure**: *um nome válido para o recurso da Fábrica de IA do Azure*
    - **Assinatura**: *sua assinatura do Azure*
    - **Grupo de recursos**: *criar ou selecionar um grupo de recursos*
    - **Região**: Selecione um dos seguintes locais\*:
        * Oeste dos EUA
        * Suécia Central
        * Leste da Austrália

    \**No momento em que este artigo está sendo escrito, há suporte para a Compreensão de Conteúdo nessas regiões.*

    ![Captura de tela das configurações do projeto.](./media/content-project-settings.png)

1. Selecione **Criar**. Aguarde a conclusão do processo de configuração. Isso pode levar alguns minutos.

## Extrair informações de uma fatura

1. Baixe [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) em `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Na página Compreensão de Conteúdo, selecione a guia **Experimentar** e, em seguida, selecione o bloco **Extração de Dados da Fatura**.

    ![Captura de tela da página "Experimentar" da Compreensão de Conteúdo.](./media/content-understanding-invoice.png)

    Uma fatura de exemplo é fornecida.

1. Selecione a fatura de exemplo e use o botão **Executar análise** para extrair informações dela. Quando a análise for concluída, visualize os resultados.

    ![Captura de tela dos resultados da análise da fatura de exemplo.](./media/sample-invoice-analysis.png)

1. Use o link **Procurar arquivos** para carregar o documento **contoso-invoice-1.pdf** que você baixou anteriormente e executar a análise nesse arquivo.

    ![Captura de tela dos resultados da análise da fatura da Contoso.](./media/contoso-invoice-analysis.png)

    Observe que o analisador de Compreensão de Conteúdo é capaz de extrair informações dessa fatura, mesmo que ela esteja formatada de forma diferente do exemplo.

1. No painel à direita, onde os campos extraídos são exibidos, acesse a guia **Resultado** para visualizar a resposta JSON que seria enviada a um aplicativo cliente. Um desenvolvedor escreveria código para processar essa resposta e utilizar os campos extraídos.

    ![Captura de tela dos resultados da análise da fatura da Contoso.](./media/invoice-analysis-json.png)

## Limpar

Se tiver terminado de usar o serviço Compreensão de Conteúdo, deve excluir os recursos que criou neste exercício para evitar incorrer em custos desnecessários do Azure.

- No portal do Azure, exclua o grupo de recursos criado para este exercício.
