---
lab:
  title: "Extrair dados\_de formulário no Estúdio de Informação de Documentos"
---

# Extrair dados de formulário no Estúdio de Informação de Documentos

A IA do Azure para Informação de Documentos é capaz de analisar e extrair informações de formulários e documentos e, em seguida, identificar nomes de campos e dados. 

Como a Informação de Documentos se baseia no reconhecimento óptico de caracteres (OCR)? Embora o OCR possa ler documentos impressos ou manuscritos, ele extrai o texto em um formato não estruturado que é difícil de armazenar em um banco de dados ou analisar. A inteligência de documentos dá sentido aos dados não estruturados, capturando a estrutura do texto, como pares de chave/valor e informações em tabelas. 

Neste exercício, você dará uma olhada em um modelo predefinido no Informação de Documentos que é treinado para reconhecer dados de recibos. 

> **OBSERVAÇÃO**: a IA do Azure para Informação de Documentos é o novo nome do Reconhecimento de Formulários do Azure. Você ainda poderá ver o Reconhecimento de Formulários do Azure no portal do Azure ou no Estúdio de Informação de Documentos.

## Criar o recurso *Informação de Documentos*

Você pode usar a IA do Azure para Informação de Documentos criando um recurso *Informação de Documentos* ou um recurso *serviços de IA do Azure*. Neste exercício, você criará o recurso *Informação de Documentos*, caso ainda não tenha um.

1. Em outra guia do navegador, abra o [Estúdio de Informação de Documentos](https://formrecognizer.appliedai.azure.com/studio), entrando com sua conta da Microsoft.
1. Selecione **Configurações** e selecione a guia **Recurso**. Selecione **Criar recurso**.
1. Na caixa de diálogo Criar recurso, insira o seguinte:
    - **Assinatura**: *sua assinatura do Azure*.
    - **Grupo de recursos**: *selecione ou crie um grupo de recursos com um nome exclusivo*.
    - **Novo nome do recurso**: *Insira um nome exclusivo*.
    - **Localização**: *Selecione uma região*.
    - **Tipo de preço**: *FO Gratuito (se disponível, caso contrário, selecione SO Standard)*.
1. Selecione **Continuar** e, em seguida, **Concluir**. Aguarde até o recurso ser implantado.

    >**Observação**: se o recurso ainda não estiver sendo exibido, talvez seja necessário **Atualizar** a página.

Mantenha o Estúdio de Informação de Documentos aberto.

## Analisar um recibo no Estúdio de Informação de Documentos

Agora você está pronto para analisar um recibo da empresa fictícia de varejo Northwind Traders.

1. Selecione [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) para baixar um documento de amostra para o seu computador. Abra a pasta . 
1. Selecione o **Estúdio de Informação de Documentos** para voltar à página **Comece a usar o Estúdio de Informação de Documentos** e, em Recibos, selecione **Experimentar**.
1. Na lista suspensa Predefinido, certifique-se de que **Recibos** esteja selecionado.
1. Selecione **Procurar arquivos** e navegue até a pasta em que a imagem foi salva. Selecione a imagem do recibo e, em seguida, **Abrir**. A imagem aparece no lado esquerdo da tela.

    ![Recibo da Northwind.](media/document-intelligence/northwind-receipt.jpg)

1. À direita, selecione **Executar análise**.
1. Quando a análise for executada, os resultados serão retornados. Observe que o serviço reconheceu campos de dados específicos, como o nome do comerciante, o endereço, o número de telefone e a data e hora da transação, bem como os itens de linha, o subtotal, o imposto e o valor total. Ao lado de cada campo há uma probabilidade percentual de que o campo esteja correto.

Neste exercício, você usou o Estúdio de Informação de Documentos para criar um recurso de Informação de Documentos. Você então usou o serviço para analisar um recibo. A partir dos resultados retornados, você viu como a Informação de Documentos foi capaz de identificar campos específicos, permitindo que os dados de documentos diários fossem processados com mais facilidade. Antes de fechar o Estúdio de Informação de Documentos, por que não experimentar alguns dos recibos de amostra, incluindo aqueles em diferentes idiomas?

## Limpeza

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Esse exercício demonstrou apenas algumas das funcionalidades do serviço IA para Informação de Documentos. Para saber mais sobre o que você pode fazer com esse serviço, confira a página [Informação de Documentos](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
