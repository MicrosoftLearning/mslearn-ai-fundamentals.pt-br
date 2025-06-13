---
title: Exercícios do Microsoft Learn — Introdução à IA no Azure
permalink: index.html
layout: home
---

# Exercícios AI-900: Introdução à IA no Azure

Esses exercícios práticos foram projetados para dar suporte ao conteúdo de treinamento no [Microsoft Learn](https://docs.microsoft.com/training/).

Para concluir os exercícios, você precisará de uma assinatura do Microsoft Azure. Inscreva-se para uma avaliação gratuita em [https://azure.microsoft.com](https://azure.microsoft.com).

{% atribuir laboratórios = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
| Exercícios |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
