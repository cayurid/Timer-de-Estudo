# Introdução

Nos últimos anos, o mercado de educação e produtividade pessoal tem experimentado um crescimento exponencial, impulsionado pela digitalização do ensino e pelo aumento do trabalho remoto. De acordo com dados da HolonIQ, o mercado global de tecnologia educacional (EdTech) deve atingir US$ 404 bilhões até 2025, com uma taxa de crescimento anual composta de 16,3%. Dentro desse cenário, ferramentas que auxiliam na gestão do tempo e na organização dos estudos ganham destaque, especialmente entre estudantes universitários, concurseiros e profissionais que buscam aprendizado contínuo.

Paralelamente, o conceito de "productivity apps" tornou-se um segmento robusto: aplicativos como Todoist, Trello e Forest acumulam milhões de usuários que buscam otimizar sua rotina. No entanto, muitas dessas soluções são genéricas ou focadas apenas em listas de tarefas, deixando uma lacuna para ferramentas especializadas em rastreamento de sessões de estudo com métricas detalhadas e gamificação. É nesse contexto que surge a oportunidade de criar um timer de estudos inteligente, que não apenas cronometra o tempo, mas também oferece insights sobre o desempenho do usuário, adaptando-se às necessidades de diferentes perfis.

Além disso, a tendência de "learning analytics" – uso de dados para melhorar a aprendizagem – está ganhando força em instituições de ensino e entre autodidatas. Um estudo da Educause aponta que 70% dos alunos acreditam que ferramentas de análise de aprendizado os ajudariam a atingir melhores resultados. Portanto, um timer integrado a um banco de dados pessoal, com capacidade de gerar relatórios de progresso, atende a essa demanda crescente por autorregulação e evidências de evolução.

## Problema

Estudantes e profissionais que buscam aprender de forma autônoma enfrentam dificuldades em manter a disciplina e medir seu progresso real. O método tradicional de "cronometrar o tempo" com um relógio comum ou aplicativos simples não oferece insights sobre a qualidade do estudo, nem permite visualizar a evolução ao longo de semanas ou meses. Além disso, muitos usuários se sentem desmotivados por não conseguirem visualizar claramente o quanto já avançaram, o que leva ao abandono dos estudos ou à procrastinação.

Outro agravante é a falta de personalização: cada pessoa tem seu ritmo, suas matérias prioritárias e seus horários mais produtivos. Ferramentas genéricas não capturam essas nuances, nem oferecem adaptações baseadas no comportamento do usuário. Por fim, em ambientes de estudo em grupo ou em instituições de ensino, professores e tutores não têm acesso a dados objetivos sobre a dedicação dos alunos, dificultando o acompanhamento e a oferta de suporte personalizado.

O problema, portanto, é a ausência de uma solução integrada que combine um timer funcional com um sistema de registro e análise de dados, capaz de empoderar o usuário a compreender seu próprio processo de aprendizado e, consequentemente, melhorar sua eficiência.

## Objetivos

Objetivo Geral:
Desenvolver uma aplicação web de timer de estudos que permita aos usuários registrar suas sessões de estudo, visualizar estatísticas de progresso e gerenciar seu tempo de forma eficiente, com diferentes níveis de acesso (usuário comum e administrador) para possibilitar escalabilidade e futuras integrações com instituições de ensino.

Objetivos Específicos:

Implementar um sistema de autenticação seguro baseado em tokens JWT, com papéis de usuário e administrador, garantindo que cada usuário tenha acesso apenas aos seus próprios dados e que administradores possam gerenciar o sistema.

Criar uma interface amigável e responsiva com timer interativo (iniciar, pausar, finalizar) e formulários para inserção de metadados (matéria, descrição), utilizando HTML, CSS e JavaScript puro no front-end.

Desenvolver uma API RESTful em C# (ASP.NET Core) que forneça endpoints para cadastro, login, CRUD de sessões de estudo e geração de relatórios agregados (horas totais por dia/semana/mês).

Estruturar um banco de dados MySQL que armazene usuários e sessões de estudo de forma normalizada, permitindo consultas eficientes para exibição de gráficos e estatísticas no front-end.

Projetar um painel administrativo com funcionalidades de gestão de usuários (listar, bloquear, visualizar estatísticas gerais) e, futuramente, geração de relatórios para acompanhamento de grupos.
 

## Justificativa

A relevância deste projeto está ancorada em três pilares: a necessidade comprovada de ferramentas de produtividade no segmento educacional, o potencial de monetização via planos premium ou institucionais, e a oportunidade de aprendizado técnico para o desenvolvedor.

De acordo com uma pesquisa da plataforma de cursos online Coursera, 87% dos alunos relatam que a falta de tempo e organização é o principal obstáculo para concluir cursos. Um timer de estudos com funcionalidades analíticas pode atacar diretamente esse ponto, fornecendo dados que ajudam o usuário a identificar padrões e ajustar sua rotina. Além disso, o mercado de aplicativos de foco e produtividade já demonstra viabilidade econômica: o Forest, por exemplo, ultrapassou 4 milhões de downloads e gera receita com versão paga e compras no aplicativo.

Do ponto de vista social, promover a educação autônoma e o aprendizado contínuo é uma forma de contribuir para a qualificação profissional em um mundo em constante mudança. A ferramenta pode ser adotada por escolas e universidades como complemento às atividades pedagógicas, auxiliando na formação de hábitos de estudo saudáveis.

Por fim, a escolha das tecnologias (HTML, CSS, JS no front-end; C# com ASP.NET Core no back-end; MySQL como banco de dados) reflete uma stack moderna, escalável e amplamente utilizada no mercado, o que garante que o projeto não apenas atenda aos requisitos funcionais, mas também sirva como um portfólio técnico de alto valor para o desenvolvedor.



## Público-Alvo

O público-alvo da aplicação é composto por dois perfis principais: o usuário comum (estudante) e o administrador (que pode ser um professor, coordenador ou gestor de grupos de estudo).

Perfil do usuário comum (estudante):

Idade: entre 16 e 40 anos.

Escolaridade: desde ensino médio até pós-graduação.

Relação com tecnologia: utiliza diariamente dispositivos como smartphone e computador, está familiarizado com aplicativos web.

Objetivos: deseja organizar melhor seu tempo de estudo, acompanhar seu progresso em diferentes disciplinas e manter a motivação por meio de métricas visuais.

Dores: procrastinação, falta de visibilidade do esforço real, dificuldade em manter consistência.

Perfil do administrador (educador/gestor):

Idade: entre 25 e 60 anos.

Profissão: professor, tutor, coordenador pedagógico, orientador de estudos.

Relação com tecnologia: utiliza ferramentas digitais para planejamento de aulas e comunicação com alunos, mas pode não ter conhecimentos técnicos avançados.

Objetivos: acompanhar a dedicação dos alunos, identificar aqueles que precisam de suporte adicional, gerar relatórios para reuniões pedagógicas.

Dores: falta de dados objetivos sobre o engajamento dos alunos, dificuldade em personalizar orientações sem métricas claras.

Personas (exemplos ilustrativos):

Ana, 22 anos, estudante de medicina. Estuda em média 8 horas por dia, mas sente que não evolui nas disciplinas. Quer visualizar quanto tempo dedica a cada matéria e comparar seu desempenho ao longo do semestre.

Carlos, 35 anos, concurseiro. Trabalha durante o dia e estuda à noite. Precisa de um timer que registre automaticamente suas sessões e mostre se está cumprindo a meta semanal de 20 horas.

Professora Mariana, 42 anos, leciona em um cursinho pré-vestibular. Gostaria de recomendar aos alunos uma ferramenta que os ajude a manter a disciplina e que lhe permita, como administradora, visualizar estatísticas agregadas da turma para ajustar o plano de ensino.

