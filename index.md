---
title: Microsoft Learn – Exercícios sobre princípios básicos de IA do Azure
permalink: index.html
layout: home
---

# Princípios Básicos de IA do Azure - Exercícios

Esses exercícios práticos foram projetados para dar suporte ao conteúdo de treinamento no [Microsoft Learn](https://docs.microsoft.com/training/).

Para concluir os exercícios, você precisará de uma assinatura do Microsoft Azure. Inscreva-se para uma avaliação gratuita em [https://azure.microsoft.com](https://azure.microsoft.com).

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions'" %}
| Exercícios |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
