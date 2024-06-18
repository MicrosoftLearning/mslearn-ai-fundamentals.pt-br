---
lab:
  title: Explorar o Copilot para Microsoft 365
---
# Explorar o Copilot para Microsoft 365

Neste exercício, você irá explorar algumas das maneiras pelas quais o Microsoft Copilot pode usar a IA gerativa para ajudá-lo a ser mais produtivo ao criar um novo conteúdo. No cenário deste exercício, você irá começar com algumas ideias de alto nível para um projeto de negócio e usar o Copilot para Microsoft 365 em diferentes aplicativos como Word, PowerPoint e Excel para auxiliar você a elaborar um plano de negócios e uma apresentação para possíveis investidores.

Este exercício levará aproximadamente **40** minutos para ser concluído.

> **Observação**: Este exercício requer uma licença do **Copilot para Microsoft 365** da sua organização.

## Usar o Copilot para explorar um documento e pesquisar uma ideia

Para iniciar a exploração da IA generativa, vamos usar o Copilot para Word para examinar um documento existente e extrair alguns insights dele.

1. No navegador da Web, abra o documento [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) em `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. 
1. Selecione **Baixar** para salvar o arquivo na pasta **Downloads** do computador.
1. **Mova** ou **copie e cole** o documento que você acabou de baixar para a pasta do **OneDrive**.
1. Na pasta do **OneDrive**, abra o **Business Idea.docx** no Microsoft Word (fechando mensagens de boas-vindas ou notificações de novos recursos) e examine o documento, que descreve algumas ideias de alto nível para um negócio de limpeza em Nova York. Se solicitado, selecione **Habilitar edição** na parte superior.
1. Localize e selecione o ícone do **Copilot** na barra de ferramentas do Word para abrir o painel Copilot, conforme mostrado aqui (seu tema visual pode variar):

    ![Captura de tela do painel Copilot no Microsoft Word.](./media/generative-ai/copilot-word-pane.png)

1. No painel Copilot, insira o seguinte prompt na área de texto na parte inferior:

    ```
    What is this document about?
    ```

1. Examine a resposta do Copilot, que deve resumir os principais pontos do documento, conforme mostrado aqui:

    ![Captura de tela do painel Copilot no Word com uma resposta.](./media/generative-ai/copilot-response-word.png)

    > A resposta específica recebida pode variar devido à natureza da IA generativa.

1. Retorne ao painel Copilot para fazer a seguinte pergunta ao Copilot:

    ```
    How do I setup a new business in New York?
    ```

1. Examine a resposta e acrescente perguntas adicionais conforme necessário. Quando estiver satisfeito com a resposta, use o ícone **Copiar** (&#128461;) na resposta para copiá-la para a área de transferência. Cole-o no documento do Word, selecione todo o texto e, em seguida, selecione o ícone Copilot (na parte inferior do texto selecionado) para visualizar o texto como uma tabela.

    ![Captura de tela solicitando que o Copilot visualize em um formato de tabela.](./media/generative-ai/copilot-rewrite-as-table.png)

1. Examine a tabela e peça ao Copilot para adicionar mais informações, como referências para obter mais detalhes.  Sua resposta deve ser semelhante a esta (talvez seja necessário usar o botão **Regenerar**):

    ![Captura de tela da resposta do Copilot em um formato de tabela.](./media/generative-ai/copilot-rewrite-as-table-response.png)

    > **Importante**: A resposta gerada por IA baseia-se em informações publicamente disponíveis na Web. Embora possa ser útil para ajudá-lo a entender as etapas necessárias para iniciar um negócio, não há garantia de que seja 100% precisa e não substitui a necessidade de orientação profissional!

1. Quando estiver satisfeito com a tabela gerada pelo Copilot, selecione a opção para **Mantê-la**.

## Usar o Copilot para criar conteúdo para um plano de negócios

Agora que você fez algumas pesquisas iniciais, vamos fazer o Copilot ajudá-lo a desenvolver um plano de negócios para sua empresa de limpeza.

1. Com o documento **Business Idea.docx** ainda aberto, no painel Copilot, insira o seguinte prompt:

    ```
    Can you suggest a name for my cleaning business?
    ```

1. Examine as sugestões e selecione um nome para sua empresa de limpeza (ou continue solicitando para encontrar um nome que você gosta).
1. No documento do Word, selecione o ícone Copilot na margem para elaborar um novo conteúdo. Insira o seguinte prompt, substituindo **Contoso Cleaning** pelo nome da empresa de sua escolha:

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

    ![Captura de tela do Copilot elaborando um plano de negócios.](./media/generative-ai/copilot-draft-business-plan-prompt.png)

1. Examine a resposta redigida pelo Copilot e mantenha-a, ajuste o tom, o tamanho ou peça ao Copilot para reescrevê-la com um novo prompt. Aplique títulos e estilo apropriados ao seu documento para torná-lo profissional. Sua resposta deverá ser semelhante a esta:

    ![Captura de tela de um documento do Word com um plano de negócios gerado pelo Copilot.](./media/generative-ai/copilot-draft-business-plan-response.png)

1. Se as projeções financeiras do plano de negócios não estiverem formatadas como uma tabela, selecione-as e use o Copilot para visualizar as projeções como uma tabela.
1. Selecione a tabela de projeções financeiras e copie-a para a área de transferência.
1. Salve o documento do Word e feche-o.

## Visualizar projeções financeiras no Copilot para Excel

Com um plano de negócios em mãos, vamos pegar alguns desses dados sobre projeções financeiras e pedir ao Copilot no Excel para visualizar esses dados para nós, para que possamos incluí-los em emails ou apresentações para investidores.

1. Abra o **Excel** e crie uma nova pasta de trabalho em branco. Salve imediatamente a pasta de trabalho como **Financial Projections.xlsx** no OneDrive, ou o Copilot não funcionará.
1. Cole a tabela de projeção de vendas do **Business Idea.docx** na planilha do Excel e **formate-a como uma tabela**. Para fazer isso:
    1. Selecione uma **célula** dentro de seus dados.
    1. Selecione **Página Inicial** e escolha **Formatar como Tabela** em Estilos. 
    1. Escolha um estilo para sua tabela.
    1. Na caixa de diálogo **Criar Tabela**, confirme ou defina o intervalo de células.
    1. Marque se a tabela tiver cabeçalhos e selecione **OK**.
1. Com as projeções de vendas formatadas como uma tabela, abra o painel do Copilot na guia **Página Inicial** da faixa de opções do Excel e insira a seguinte solicitação:

    ```
    Suggest ways to visualize these financial projections.
    ```
    
1. O Copilot deve sugerir uma maneira de visualizar seus dados e oferecer para adicionar um gráfico dinâmico a uma nova planilha.

    ![Captura de tela do Copilot no Excel visualizando projeções financeiras.](./media/generative-ai/copilot-excel-visualize-projections.png)

1. Adicione o gráfico dinâmico a uma nova planilha e abra-o. Selecione o gráfico e selecione **Design** para aplicar estilos, alterar o tipo de gráfico e outras ações. No final, você deve ter algo semelhante a isto:

    ![Captura de tela do Copilot no Excel adicionando um Gráfico Dinâmico.](./media/generative-ai/copilot-excel-chart-design.png)

1. Salve a pasta de trabalho e feche o Excel.

Você acabou de usar dados criados do Copilot no Word para visualizá-los no Excel. No próximo exercício, você vai passar a usar o Copilot no Outlook para redigir e enviar emails sobre o trabalho que você fez.

## Usar o Copilot para redigir um email

Você criou alguns materiais de apoio para ajudar a iniciar seu negócio. Agora é hora de entrar em contato com um investidor em busca de financiamento de startup.

1. Abra o **Outlook**. Se você não configurou o Outlook com sua conta do Microsoft 365, faça isso.

    > **Dica**: Confira [Configurar e usar o Outlook – Suporte da Microsoft](https://support.microsoft.com/office/set-up-and-use-outlook-4636f361-d5e3-4a87-9cd4-382858de55fa) para obter ajuda com isso.

1. Na barra de ferramentas, alterne para a experiência do**novo Outlook** se ela ainda não estiver ativa.

    > **Observação**: Para obter os recursos mais recentes do Copilot no Outlook, você deve estar usando a experiência "Novo Outlook". Para ver qual versão você está usando, consulte [Qual versão do Outlook eu tenho? – Suporte da Microsoft](https://support.microsoft.com/office/what-version-of-outlook-do-i-have-b3a9568c-edb5-42b9-9825-d48d82b2257c).

1. Crie um novo email e preencha a caixa **Para** com seu próprio endereço de email.
1. Você pode começar a redigir seu email no painel Copilot ou diretamente de dentro do corpo do email:

    ![Captura de tela do Outlook e as opções para elaborar um email com o Copilot.](./media/generative-ai/copilot-draft-email-outlook.png)
    
1. Insira a seguinte solicitação e ajuste as opções para definir o tom como "Formal" e o comprimento como "Médio":

    ```
    Request a meeting with an investment bank to discuss funding for a commercial cleaning business.
    ```

    ![Captura de tela da redação de um email com o Copilot no Outlook.](./media/generative-ai/copilot-draft-email-adjust-tone-outlook.png)

1. Selecione **Gerar rascunho** e examine a saída gerada. Ajuste o tom ou diga ao Copilot o que você gostaria de alterar no email.

    ![Captura de tela do email gerado com o Copilot no Outlook.](./media/generative-ai/copilot-draft-email-results-outlook.png)

1. Você pode enviar o email para si mesmo, se desejar!

## Usar o Copilot para criar conteúdo para uma apresentação

Com a ajuda do Copilot, você criou um rascunho de um plano de negócios para a ideia de negócios de limpeza, preparou algumas projeções financeiras e enviou um email para solicitar uma reunião com um potencial investidor. Agora você precisará de uma apresentação eficaz para comunicar os benefícios do seu negócio.

1. Abra o **PowerPoint** e crie uma nova **apresentação em branco**. Se o painel **Designer** for aberto automaticamente, feche-o.

    ![Captura de tela da criação de uma nova apresentação em branco no PowerPoint.](./media/generative-ai/powerpoint-create-blank-presentation.png)

1. Salve a apresentação como **Cleaning Company.pptx** na pasta do OneDrive.
1. Selecione o **botão Copilot** na **guia Página Inicial** da faixa de opções, selecione **Criar apresentação sobre...** e, em seguida, preencha o prompt no painel Copilot da seguinte maneira:

    ```
    Create a presentation about a corporate cleaning service in New York City.
    ```

1. O Copilot irá gerar slides na apresentação.  O processo pode levar vários minutos e sua saída deve ser semelhante a esta com um tema diferente:

    ![Captura de tela da apresentação do PowerPoint criada pelo Copilot de um documento do Word.](./media/generative-ai/copilot-powerpoint-create-image.png)

1. Selecione o penúltimo slide na apresentação. Em seguida, no painel do Copilot, use a solicitação **Adicionar um slide sobre...** para criar um novo slide sobre `the benefits of an eco-friendly approach to cleaning.`

    ![Captura de tela da apresentação do PowerPoint para criar um novo slide.](./media/generative-ai/copilot-powerpoint-add-new-slide.png)

1. Salve a apresentação.

## Desafio

Agora você viu como usar o Copilot para Microsoft 365 em alguns aplicativos diferentes para pesquisar ideias e gerar conteúdo. Por que não tentar explorar mais? Tente usar o Copilot para elaborar um plano de evento que promova a alfabetização infantil em uma biblioteca local. Algumas coisas que você pode tentar incluem:

- Pesquisar algumas dicas para incentivar as crianças a lerem desde cedo.
- Criar um folheto ou pôster para o evento.
- Redigir um email para uma campanha para convidar autores infantis locais para vir falar no evento.
- Criar uma apresentação para iniciar o evento.

Seja tão inventivo quanto quiser e explore como o Copilot pode ajudá-lo a encontrar informações, gerar e aprimorar textos, criar imagens e responder perguntas.

## Conclusão

Neste exercício, você usou o [Copilot para Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365) para localizar informações e gerar conteúdo. Espero que você tenha visto como usar a IA generativa em um Copilot pode ajudar na produtividade e criatividade. O Microsoft 365 permite que você traga o poder da IA gerativa para seus dados e processos empresariais, ao mesmo tempo em que se integra à sua infraestrutura de TI existente para garantir uma solução gerenciável e segura.
