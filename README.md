# PSE em Ação

**Sistema de Planejamento e Acompanhamento de Ações de Saúde na Escola**

Projeto acadêmico desenvolvido para a Atividade de Estudo Programada (AEP) do 2º semestre de 2026 dos cursos de Engenharia de Software / Análise e Desenvolvimento de Sistemas da UniCesumar.

## 1. Objetivo

Desenvolver uma aplicação introdutória em linguagem C para apoiar o cadastro, a consulta e o acompanhamento de ações coletivas do Programa Saúde na Escola (PSE), com apresentação de informações gerais sobre planejamento e participação.

## 2. Funcionalidades

1. **Cadastrar ação:** registra código, escola, tema, data prevista, público-alvo, responsável, quantidade prevista de participantes e situação inicial planejada.
2. **Listar ações:** apresenta todos os registros cadastrados.
3. **Pesquisar ações:** permite localizar registros por código, escola ou tema. A pesquisa textual aceita parte do nome e não diferencia maiúsculas de minúsculas.
4. **Atualizar situação:** altera a situação para planejada, realizada ou cancelada. Quando a ação é marcada como realizada, solicita a quantidade efetiva de participantes.
5. **Gerar resumo geral:** apresenta a quantidade de ações por situação, participantes previstos, participantes efetivos e percentual de participação.
6. **Encerrar:** finaliza a execução.

## 3. Tecnologias e conceitos utilizados

- Linguagem C (padrão C99 ou posterior).
- `struct` para representar uma ação.
- Vetor com capacidade máxima de 100 ações.
- Funções para separar responsabilidades.
- Estruturas condicionais (`if`, `else`, `switch`).
- Laços de repetição (`for`, `do while`).
- Validação de entradas e prevenção de códigos duplicados.

## 4. Requisitos

É necessário ter um compilador C instalado, como GCC ou Clang. O sistema funciona em terminal/linha de comando.

## 5. Compilação e execução

Na raiz do repositório, execute:

### Linux

```bash
gcc -std=c99 -Wall -Wextra -pedantic src/main.c -o pse
./pse
```

### Windows (MinGW/GCC)

```bash
gcc -std=c99 -Wall -Wextra -pedantic src/main.c -o pse.exe
pse.exe
```

Também é possível abrir `src/main.c` em uma IDE que ofereça suporte a C, configurar o projeto como **C** (não C++) e compilar.

## 6. Regras de funcionamento e interpretação do resumo

- O código da ação deve ser positivo e não pode se repetir.
- Escola, tema, data prevista, público-alvo e responsável são campos obrigatórios.
- As quantidades de participantes não podem ser negativas.
- A situação inicial de toda ação cadastrada é **Planejada**.
- O limite de armazenamento é de 100 ações por execução.
- O percentual é calculado por: `participantes efetivos das ações realizadas / participantes previstos de todas as ações cadastradas * 100`.
- Se o total previsto for zero, o percentual apresentado será 0,00% para evitar divisão por zero.
- O total de participantes efetivos considera somente ações marcadas como realizadas.

## 7. Limitações conhecidas

- Os registros ficam somente na memória durante a execução. Ao encerrar o programa, os dados são perdidos. O enunciado permite armazenamento em memória e considera o uso de arquivos uma melhoria opcional.
- O campo de data é solicitado no formato `DD/MM/AAAA`, mas esta versão não valida se a data existe no calendário.
- O sistema não cadastra dados pessoais ou clínicos de estudantes e não realiza diagnóstico, triagem, prescrição ou recomendação de tratamento.
- Os dados utilizados na demonstração devem ser fictícios e coletivos.

## 8. Estrutura do repositório

```text
pse-em-acao/
├── src/
│   └── main.c
├── docs/
│   ├── roteiro_video.md
│   └── casos_de_teste.md
├── tests/
│   └── README.md
└── README.md
```

## 9. Integrantes

Preencher antes da entrega:

- Integrante 1: **[NOME COMPLETO]**
- Integrante 2: **[NOME COMPLETO]**
- Integrante 3 (se houver): **[NOME COMPLETO]**

## 10. Natureza acadêmica e privacidade

Este projeto tem finalidade acadêmica e utiliza dados fictícios. O sistema trabalha com informações coletivas das ações, sem registrar nome, diagnóstico, prontuário, condição clínica ou qualquer dado sensível individual de estudantes.
