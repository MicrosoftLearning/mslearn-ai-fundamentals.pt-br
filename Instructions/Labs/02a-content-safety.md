# Explorar a Segurança de Conteúdo na Fábrica de IA do Azure

Os serviços de IA do Azure ajudam os usuários a criar aplicativos de IA com APIs e modelos prontos para uso, predefinidos e personalizáveis. Neste exercício, você analisará um dos serviços, a Segurança de Conteúdo de IA do Azure, que permite moderar o conteúdo de texto e imagem. No portal da Fábrica de IA do Azure, a plataforma da Microsoft para criar aplicativos inteligentes, você usará a Segurança de Conteúdo de IA do Azure para categorizar o texto e atribuir a ele a pontuação de gravidade. 

> **Observação** A meta deste exercício é obter uma noção geral de como os serviços de IA do Azure são provisionados e usados. A Segurança de Conteúdo é usada como exemplo, mas não se espera que você obtenha um conhecimento abrangente da segurança de conteúdo neste exercício!

## Criar um projeto no portal do Foundry da IA do Azure

1. Em uma guia do navegador, navegue até o [portal da Fábrica de IA do Azure](https://ai.azure.com?azure-portal=true).

2. Entre com sua conta. 

3. Na home page do portal da Fábrica de IA do Azure, selecione **Criar um projeto**. Na Fábrica de IA do Azure, os projetos são contêineres que ajudam a organizar o trabalho.  

    ![Captura de tela da home page da Fábrica de IA do Azure com "Criar um projeto" selecionado.](./media/azure-ai-foundry-home-page.png)

4. No painel *Criar um projeto*, você verá um nome de projeto gerado, que pode ser mantido como está. Caso tenha criado um hub no passado, você verá uma lista de *novos* recursos do Azure a serem criados ou uma lista suspensa de hubs existentes. Se você vir a lista suspensa de hubs existentes, selecione *Criar novo hub*, crie um nome exclusivo para seu hub e selecione *Avançar*.  
 
    ![Captura de tela do painel criar um projeto com nomes gerados automaticamente para hub e projeto.](./media/azure-ai-foundry-create-project.png)

> **Importante**: você precisará de um recurso de serviços de IA do Azure provisionado em um local específico para concluir o restante do laboratório.

5. No mesmo painel *Criar um projeto*, selecione **Personalizar** e selecione um dos seguintes **locais**: Leste dos EUA, França Central, Coreia Central, Oeste da Europa ou Oeste dos EUA para concluir o restante do laboratório. Em seguida, selecione **Criar**. 

1. Anote os recursos criados: 
- Serviços de IA do Azure
- Hub de IA do Azure
- Projeto de IA do Azure
- Conta de armazenamento
- Key vault
- Grupo de recursos  

6. Depois que os recursos forem criados, a página *Visão geral* do projeto abrirá. 

7. Para usar a Segurança de Conteúdo, você precisa fazer uma atualização de permissões para o recurso do *hub de IA do Azure*. Para fazer isso, abra o [portal do Azure](https://portal.azure.com?portal-azure=true) e entre com a mesma assinatura usada para criar seus recursos da Fábrica de IA.  

8. No portal do Azure, use a barra de busca na parte superior da página para buscar e selecionar a **Fábrica de IA do Azure**. Na página de recursos, selecione o recurso que você acabou de criar que é do *tipo***hub de IA do Azure**.  

9. No portal do Azure, no painel esquerdo, selecione **Controle de Acesso (IAM)**. Em seguida, no painel aberto, selecione **Adicionar** ao lado do sinal de mais e selecione **Adicionar atribuição de função**. 

![Captura de tela de onde selecionar adicionar atribuição de função no painel Controle de Acesso.](./media/content-safety/access-control-step-one.png)

10. Pesquisa **Avaliador de Segurança da IA do Azure** na lista de funções e selecione-o. Em seguida, selecione **Avançar**. 

11. Use as seguintes configurações para atribuir-se à função: 
    - **Atribuir acesso a**: selecione *usuário, grupo ou entidade de serviço*
    - **Membros**: clique em *selecionar membros*
        - No painel aberto *Selecionar membros*, encontre seu nome. Clique no ícone de adição ao lado do seu nome. Em seguida, clique em **Selecionar**.
    - **Descrição**: *deixe em branco*

12. Selecione **Revisar e atribuir** e selecione **Revisar e atribuir** novamente para adicionar a atribuição de função.    

13. No navegador, volte ao [portal da Fábrica de IA do Azure](https://ai.azure.com?azure-portal=true). Selecione o projeto. 

14. No menu à esquerda da tela, selecione **Serviços de IA**.
 
    ![Captura de tela do menu à esquerda da tela do projeto com os Serviços de IA selecionados.](./media/azure-ai-foundry-ai-services.png)  

15. Na página *Serviços de IA*, clique no bloco *Visão + Documento* para experimentar os recursos Visão de IA do Azure e Documento.
    
    ![Captura de tela do bloco Segurança de Conteúdo.](./media/content-safety-tile.png)

## Experimentar a moderação de texto com a Segurança de Conteúdo no portal da Fábrica de IA do Azure 

1. Na página *Segurança de Conteúdo*, em *Filtrar conteúdo do texto*, selecione **Moderar conteúdo do texto**.

2. Na página *Moderar conteúdo do texto*, no título *Experimentar*, selecione o recurso de serviços de IA do Azure que você acabou de criar no menu suspenso.   

3. Em *Executar um teste simples*, selecione o bloco **Conteúdo Seguro**. Observe que o texto é exibido na caixa abaixo. 

4. Clique em **Executar teste**. Executar um teste chama o modelo de aprendizado profundo do serviço de Segurança de Conteúdo. O modelo de aprendizado profundo já foi treinado para reconhecer conteúdo não seguro.

5. No painel *Resultados*, inspecione os resultados. Há quatro níveis de gravidade, de seguro a alto, e quatro tipos de conteúdo prejudicial. O serviço de IA de Segurança de Conteúdo considera esse exemplo aceitável ou não? O que é importante observar é que os resultados estão dentro de um intervalo de confiança. Um modelo bem treinado, como um dos modelos prontos para uso da IA do Azure, pode retornar resultados que têm uma alta probabilidade de corresponder ao que um humano rotularia o resultado. Sempre que você executa um teste, você chama o modelo novamente. 

6. Agora, tente outra amostra. Selecione o texto em Conteúdo violento com erro de ortografia. Verifique se o conteúdo é exibido na caixa abaixo.

7. Selecione **Executar teste** e inspecione os resultados no painel Resultados novamente. 

Execute testes em todos os exemplos fornecidos e inspecione os resultados.

## Limpar

Se você não pretende fazer mais exercícios, exclua todos os recursos de que não precisa mais. Isso evita o acúmulo de custos desnecessários.

1. Abra o [portal do Microsoft Azure]( https://portal.azure.com) e selecione o grupo de recursos que contém o recurso que você criou.
1. Selecione o recurso e selecione **Excluir** e, em seguida, **Sim** para confirmar. Em seguida, o recurso é excluído.

## Saiba mais

Este exercício demonstrou apenas algumas das funcionalidades do serviço de Segurança de Conteúdo. Saiba mais sobre o que você pode fazer com esse serviço na [página Segurança de Conteúdo](https://learn.microsoft.com/azure/ai-services/content-safety/overview).
