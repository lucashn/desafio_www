# Website - Desafio de Programação

Sítio para compilar informações relevantes para o projeto de ensino "Desafio de Programação", com exemplos de código, tutoriais e informações sobre eventos anteriores.

Como só eu irei atualizar a página, não há necessidade de implementar um sistema dinâmico, com usuários e etc. Basta um site estático.

Entre utilizar um gerador de páginas estáticas, como o Jekyll, e escrever um aplicativo utilizando uma biblioteca de frontend (Vue), optei pelo primeiro, por simplicidade de desenvolvimento e para exigir menos recursos do leitor.

## Requisitos

- Mostrar informações sobre a edição atual do desafio de programação, de forma destacada
- Mostrar informações sobre edições anteriores
- Compilar tutoriais, exemplos de código e exemplos de solução de problemas da OBI e Maratona de Programação
- O tema deve ser simples e funcionar bem tanto em desktops quanto smartphones

Obs.: a página não servirá para comunicações rápidas entre professor / estudante, sendo reservado para isto o e-mail.

## Manutenção e hospedagem

O sítio será hospedado no Firebase por praticidade, e o código hospedado no Bitbucket. Utilizarei o serviço CircleCI para automatizar o *deploy*, conforme o tutorial publicado por Chris em 2017 [1].

[1]: https://chris.banes.dev/2017/06/02/jekyll-firebase/
