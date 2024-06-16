---
lab:
  title: Explorar o Copilot no Microsoft Edge
---
# Explorar o Microsoft Copilot no Microsoft Edge

Nesse exercício, você irá explorar algumas das maneiras pelas quais o Microsoft Copilot pode usar a IA generativa para ajudar você a ser mais produtivo quando criar um novo conteúdo. No cenário criado para esse exercício, você vai começar com algumas anotações de alto nível para uma ideia de negócios e usar o Copilot no Microsoft Edge, que ajudará você a desenvolver um plano de negócios e uma apresentação para possíveis investidores.

Este exercício levará aproximadamente **40** minutos para ser concluído.

> **Observação**: esse exercício pressupõe que você tenha uma [Conta Microsoft pessoal](https://signup.live.com) (como uma conta do outlook.com) com a qual fez login no [Microsoft Edge](https://www.microsoft.com/edge/download) no seu computador.

## Usar o Copilot para explorar um documento e pesquisar uma ideia

Para iniciar sua exploração da IA generativa, vamos usar o Microsoft Copilot no Edge para examinar um documento existente e extrair alguns insights.

1. No Microsoft Edge, navegue até o [OneDrive](https://onedrive.live.com) em `https://onedrive.live.com` e entre usando sua conta pessoal da Microsoft. Feche as mensagens de boas-vindas ou ofertas que aparecem.
1. Em outra guia do navegador, abra o documento [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) de `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. Em seguida, quando o documento for aberto no Edge, selecione a opção **Salvar uma cópia no OneDrive** e salve o documento na sua pasta **Documentos** no OneDrive. O documento deve ser aberto em seguida no Microsoft Word online automaticamente.

    > **Dica**: se não estiver vendo a opção de salvar uma cópia do arquivo no OneDrive, baixe-o para o seu computador local. Em seguida, no OneDrive, abra a pasta **Documentos** e use o botão **+ Adicionar novo** para carregar o arquivo **business Idea.docx** do seu computador local para o OneDrive.

1. Visualize o texto no **Business Idea.docx**, que descreve algumas ideias de alto nível para uma empresa de limpeza na cidade de Nova York.
1. Use o ícone do **Copilot** na barra de ferramentas do Edge para abrir o painel do Copilot, conforme mostrado aqui:

    ![Captura de tela do painel do Copilot no Microsoft Edge.](./media/generative-ai/edge-copilot.png)

1. No painel do Copilot, role para baixo para ver todo o conteúdo conforme necessário e certifique-se de que a guia **Chat** esteja selecionada e o estilo de conversação esteja definido como **Mais Equilibrado**, o que irá garantir que o Copilot responda com um equilíbrio entre criatividade e precisão factual.
1. Na caixa do chat, na parte inferior do painel do Copilot, insira o seguinte prompt:

    ```
    What is this document about?
    ```

    Se solicitado, confirme que você quer permitir que o Copilot acesse a página.

1. Leia a resposta do Copilot, que deve resumir os pontos principais do documento, conforme mostrado aqui:

    ![Captura de tela do painel do Copilot com uma resposta.](./media/generative-ai/copilot-response.png)

    > **Observação**: a resposta específica pode variar.

1. Digite a seguinte solicitação:

    ```
    How do I go about setting up a business in New York?
    ```

1. Leia a resposta, que deve conter alguns conselhos e links para o recurso que ajudará você a começar a estabelecer uma empresa em Nova York, podendo incluir alguns prompts de sugestão de acompanhamento para obter mais informações.

    > **Importante**: a resposta gerada pela IA se baseia em informações publicamente disponíveis na web. Embora possa ser útil para ajudar você a entender as etapas necessárias para estabelecer uma empresa, não podemos garantir que seja 100% precisa e não deve substituir a necessária consultoria profissional.

## Usar o Copilot para criar conteúdo para um plano de negócios

Agora que você já fez algumas pesquisas iniciais, vamos pedir ao Copilot para ajudar você a desenvolver um plano de negócios para a sua empresa de limpeza.

1. Com o documento **Business Idea.docx** ainda aberto no Microsoft Edge, insira o seguinte prompt no painel do Copilot:

    ```
    Suggest a name for my cleaning business
    ```

1. Leia as sugestões e selecione um nome para a sua empresa de limpeza (ou continue escrevendo prompts até encontrar um nome de que você goste).
1. Insira o seguinte prompt, substituindo *Contoso Cleaning* pelo nome da empresa que você escolher:

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

1. Leia a resposta e, no resultado, use o ícone **Copiar** (&#128461;) para copiá-la para a área de transferência. Em seguida, selecione todo o texto do documento **Business Ideas.docx** e cole o texto copiado no documento para substituí-lo. Para concluir, termine de editar o texto colado substituindo o texto inicial na resposta (na qual Copilot reconheceu a instrução) por um cabeçalho com o nome da sua empresa de limpeza. Você deve terminar com um documento de plano de negócios semelhante ao seguinte:

    ![Captura de tela de um documento do Word com um plano de negócios gerado pelo Copilot.](./media/generative-ai/generated-content.png)

1. No painel do Copilot, insira o seguinte prompt:

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```

1. Leia a resposta, que deve apresentar quatro opções para um logotipo criado pelo Microsoft Designer.
1. Use mais prompts para iterar no design (por exemplo, `Make it green and blue`) até obter um logotipo que lhe agrade.
1. Clique com o botão direito do mouse no design do logotipo de sua preferência e o copie para a área de transferência. Em seguida, cole-o na parte superior do documento do plano de negócios, assim:

    ![Captura de tela de um documento do Word com uma imagem gerada pelo Copilot.](./media/generative-ai/generated-image.png)

1. Feche a guia do Microsoft Word e volte à pasta **Documentos** no seu OneDrive.

## Usar o Copilot para criar conteúdo para uma apresentação

Com a ajuda do Copilot, você criou um rascunho de um plano de negócios para a sua ideia de uma empresa de limpeza. Agora você precisará de uma apresentação eficaz para convencer um investidor a lhe emprestar o dinheiro necessário para começar a empresa.

1. Na pasta **Documentos** do OneDrive, adicione uma nova **Apresentação do PowerPoint**.

    Se o painel do **Designer**abrir automaticamente, feche-o.

1. No slide de título da apresentação, insira o nome da sua empresa de limpeza como título e `Investor Opportunity` como subtítulo.
1. Adicione um novo slide usando o layout de slides **Dois Conteúdos** (que inclui um título e dois espaços reservados para o conteúdo).
1. Altere o título do slide para `Benefits of Hiring a Commercial Cleaner`.
1. No painel do Copilot, insira o seguinte prompt:

    ```
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Copie a resposta do Copilot para a área de transferência e cole-a no espaço reservado para o conteúdo no lado esquerdo. Em seguida, exclua a sentença inicial em que a solicitação foi reconhecida e reformate o texto no espaço reservado até que fique ao seu gosto.
1. No painel do Copilot, insira o seguinte prompt:

    ```
    Create a photorealistic image of a clean office.
    ```

1. Quando o Copilot gerar uma imagem que lhe agradar, você deve copiá-la para a área de transferência e colá-la no espaço reservado para o conteúdo no lado direito do slide.

    Se o painel do **Designer** abrir automaticamente, selecione um design de slide que lhe agrade. Em seguida, feche o painel do **Designer**.

1. Aplique qualquer reformatação adicional que você achar necessária até obter um slide semelhante ao seguinte:

    ![Captura de tela de uma apresentação do PowerPoint com conteúdo gerado pelo Copilot.](./media/generative-ai/powerpoint-slide.png)

1. Na barra de título do PowerPoint, selecione o nome da apresentação padrão (**Apresentação**) e o renomeie como `Business Presentation.pptx`.
1. Feche a guia do PowerPoint e volte à pasta **Documentos** no seu OneDrive.

## Usar o Copilot para redigir um email

Você criou algumas garantias que ajudarão você a começar seu negócio. Agora chegou a hora de entrar em contato com um investidor em busca de um financiamento para novas empresas.

1. Use o **Inicializador de Aplicativos** na ponta esquerda da barra de título do OneDrive para abrir o **Outlook**.
1. Crie um novo email e preencha a caixa **Para** com seu próprio endereço de email.
1. No painel do Copilot, selecione a guia **Redigir**. Em seguida, defina as seguintes opções para redigir o novo conteúdo:
    - **Escreva sobre**: `Request a meeting with an investment bank to discuss funding for a commercial cleaning business.`
    - **Tom**: Profissional
    - **Formato**: Email
    - **Comprimento**: Médio
1. Selecione **Gerar rascunho** e leia o resultado que for gerado.
1. Use o conteúdo gerado para preencher seu email, conforme mostrado aqui:

    ![Captura de tela de uma mensagem de email gerada pelo Copilot.](./media/generative-ai/generated-email.png)

    Você pode enviar o email para o seu próprio endereço, se quiser!

## Desafio

Agora que você já viu como usar o Copilot para pesquisar ideias e gerar conteúdo, por que não tenta explorar ainda mais? Para iniciar uma nova sessão do Copilot, na guia **Chat**, selecione o ícone **Novo tópico** ao lado da caixa de prompt e tente usar o Copilot para planejar um evento para promover a alfabetização de crianças em uma biblioteca local. Algumas coisas que você pode tentar incluem:

- Pesquisar algumas dicas para incentivar crianças a ler desde cedo.
- Criar um folheto ou um pôster para o evento.
- Redigir um email para uma campanha convidando autores de livros infantis locais a fazer uma palestra no evento.
- Criar uma apresentação para dar início ao evento.

Use sua criatividade como quiser e explore como o Copilot pode ajudar você encontrando informações, gerando e refinando o texto, criando imagens e respondendo perguntas.


## Conclusão

Nesse exercício, você usou o Copilot no Microsoft Edge para encontrar informações e gerar conteúdo. Espero que você tenha entendido como usar a IA generativa em um Copilot pode ajudar a aumentar sua produtividade e criatividade.

Embora os serviços gratuitos usados nesses exercícios sejam, com certeza, muito poderosos, você pode obter resultados ainda melhores com serviços como o [Copilot para Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365), em que o Microsoft Copilot é integrado aos aplicativos de produtividade do Windows e do Microsoft Office para fornecer uma ajuda altamente contextualizada nas tarefas comuns. O Microsoft 365 permite que você adicione o poder da IA generativa aos seus dados e processos de negócios e, ao mesmo tempo, integre o recurso à sua infraestrutura de TI existente para garantir uma solução segura e fácil de usar.