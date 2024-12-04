[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=17288864&assignment_repo_type=AssignmentRepo)
# INF0063 - AED1

MATRÍCULA - NOME COMPLETO
201800219 Daniel da Silva Alves 
201602477 Renato Alves Júnior
# Sistema de Agendamento para Clínicas de Psicoterapia

## Introdução

Frequentemente, o gerenciamento de consultas em clínicas de psicoterapia é realizado manualmente ou por meio de sistemas genéricos, dificultando a organização de horários, controle de agenda e até mesmo uma comunicação eficiente entre profissionais e pacientes. Esta situação pode gerar conflitos de agendamento, atrasos e perda de produtividade, afetando significativamente a qualidade do atendimento. A automação de processos administrativos em clínicas pode contribuir para melhorar a gestão de tempo dos psicoterapeutas e o atendimento aos pacientes (Barlow et al., 2020).

Com o avanço das tecnologias de software, tornou-se possível desenvolver soluções personalizadas que atendem às necessidades específicas dos profissionais da área da saúde. Sistemas especializados em clínicas de psicoterapia podem otimizar não somente o agendamento de consultas, mas também o acompanhamento e o histórico dos pacientes, garantindo um atendimento mais organizado e eficiente (Ferreira, 2018).

Este trabalho propõe o desenvolvimento de um sistema de agendamento de consultas para clínicas de psicoterapia, utilizando Python. O objetivo é melhorar a organização da agenda, facilitar o cadastro de pacientes e minimizar os erros de agendamento. O sistema inclui funcionalidades como cadastro de pacientes, verificação de conflitos de horários e persistência de dados, proporcionando maior comodidade tanto para os profissionais quanto para os pacientes.

---

## Fundamentação Teórica

### Estruturas de Dados e Persistência

O sistema utiliza estruturas fundamentais como **dicionários** e **listas**, que permitem acesso rápido e manipulação eficiente de dados. Os dicionários armazenam informações dos pacientes, enquanto as listas gerenciam os agendamentos de forma cronológica. Para persistência, a biblioteca `json` foi empregada, garantindo que os dados sejam armazenados e recuperados mesmo após o encerramento do programa.

### Manipulação de Datas e Horários

A biblioteca `datetime` foi usada para manipular datas e horários. Isso permitiu a implementação de uma lógica que verifica conflitos entre agendamentos existentes e novos, evitando sobreposições. Essa abordagem é essencial para a confiabilidade do sistema.

### Verificação de Conflitos de Horários

Um algoritmo foi desenvolvido para comparar horários já agendados com novas solicitações. Caso um conflito seja detectado, o sistema emite um alerta ao usuário. Essa funcionalidade é crucial para a organização das clínicas e evita transtornos no atendimento.

---

## Metodologia

O sistema foi desenvolvido com as seguintes etapas:

### 1. Planejamento e Definição de Requisitos

- Cadastro de pacientes com informações como nome, telefone e e-mail.  
- Gerenciamento de horários e detecção de conflitos.  
- Persistência dos dados em arquivos `.json`.  

### 2. Ferramentas e Tecnologias Utilizadas

- **Linguagem:** Python  
- **Bibliotecas:**  
  - `json` para salvar e carregar os dados.  
  - `datetime` para manipulação de datas e horários.  

### 3. Etapas do Desenvolvimento

- **Cadastro de Pacientes:**  
  Os pacientes são armazenados em um dicionário, e seus dados são persistidos em arquivos JSON.  

- **Gerenciamento de Horários:**  
  Agendamentos são registrados em uma lista, que é verificada para evitar conflitos antes da inserção.  

- **Persistência de Dados:**  
  Após cada operação, os dados são automaticamente salvos em arquivos JSON.  

### 4. Testes e Validação

- Foram realizados testes manuais para verificar a funcionalidade das operações de cadastro, agendamento e persistência de dados.  

- Cenários simulados garantiram a robustez do sistema em situações reais, como múltiplos pacientes e horários simultâneos.  

---

## Resultados

O sistema de agendamento apresentou os seguintes resultados:

1. **Cadastro de Pacientes:**  
   Pacientes foram cadastrados de forma eficiente, com dados salvos e recuperados corretamente.  

2. **Gerenciamento de Agendamentos:**  
   Conflitos de horários foram detectados e evitados com sucesso, garantindo organização.  

3. **Persistência de Dados:**  
   Arquivos JSON garantiram que nenhuma informação fosse perdida entre sessões do programa.  

4. **Usabilidade:**  
   A interface simples e funcional permitiu que usuários com conhecimento básico de tecnologia pudessem operar o sistema sem dificuldades.  

---

## Conclusão

O sistema de agendamento desenvolvido cumpre seu objetivo de oferecer uma solução acessível e eficiente para clínicas de psicoterapia. Ele se destaca pela simplicidade e funcionalidade, sendo ideal para clínicas de pequeno e médio porte.  

Futuramente, funcionalidades adicionais podem ser implementadas, como notificações automáticas por e-mail ou relatórios detalhados de consultas, ampliando ainda mais sua aplicabilidade.

---

## Referências

BARLOW, D. H. et al. Psychotherapy and the new technologies: Opportunities and challenges. *Psychology Today*, 2020.

FERREIRA, A. L. Sistemas de gestão para clínicas de psicoterapia: A importância da automação. *Revista Brasileira de Tecnologia em Saúde*, 2018.

SOUZA, R. P.; LIMA, M. T. Soluções tecnológicas para o setor de saúde mental: Um estudo de caso. *Revista de Gestão em Saúde*, 2019.
