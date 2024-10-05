# Desafio - Modelagem Criando um Star Schema para Cenários de Vendas com Power BI

## Objetivo


Criar o diagrama dimensional – star schema – com base no diagrama relacional disponibilizado.

O foco desta análise são os professores e com este objeto de análise iremos montar o esquema em estrela com o foco na análise dos dados dos professores. Sendo assim, a tabela fato deve refletir diversos dados sobre professor, cursos ministrados, departamento ao qual faz parte, etc. Esse deve ser o direcionamento que deve guiar a construção da tabela fato do modelo em questão.  Da mesma forma, é necessária a criação das tabelas dimensão que serão compostas pelos detalhes relacionados ao contexto.

Por fim, mas não menos importante, devemos adicionar uma tabela dimensão de datas para compensar a falta de dados do tipo datas do modelo relacional.

## Desenvolvimento

Para criar os diagramas de relacionamentos foi utilizado a ferramenta [sqlDBM](https://app.sqldbm.com/). Inicialmente replicamos o diagrama apresentado no desafio com esta ferramenta, e apresentamos aqui: [diagrama transacional](./diagrama_relacionamento_transacional.png).

Posteriomente pensamos em quais perguntas podem ser válidas para construir a modelagem dimensional que eficiente para analisar o seguinte o contexto dos professores. Assim, elaboramos os seguintes questionamentos:

01. Quantas disciplinas cada professor ministra por semestre ou ano?
02. Qual é a carga horária total ministrada por cada professor em um período específico?
03. Quais são as disciplinas ministradas por cada professor?
04. Quantas disciplinas em um determinado curso são ministradas por um professor?
05. Em quais departamentos cada professor está alocado?
06. Quantas disciplinas um professor ministra em cada departamento?
07. Em quais campi os professores estão alocados?
08. Qual é a distribuição de professores por departamento?
09. Quais disciplinas ministradas por um professor têm pré-requisitos?
10. Quais professores ministram disciplinas com maior número de pré-requisitos?
11. Quais professores são responsáveis por disciplinas em mais de um departamento?
12. Quais disciplinas ministradas por professores pertencem a mais de um curso?
13. Quantos cursos diferentes estão associados a disciplinas ministradas por cada professor?
14. Quantas disciplinas com pré-requisitos são ministradas por um professor em cada semestre?
15. Quantos professores estão associados a cada departamento e quantas disciplinas cada um ministra?
16. Quantas disciplinas um professor leciona por curso ao longo de um ano?
17. Quantos professores lecionam no mesmo departamento em campi diferentes?
18. Quais são as disciplinas ministradas por mais de um professor em um mesmo curso?
19. Quantos professores têm múltiplos vínculos em diferentes departamentos?
20. Qual a distribuição de disciplinas entre os professores que lecionam em mais de um curso?

O foco dessa análise são os professores inseridos no contexto de disciplinas e cursos. Para isso, aplicamos a seguinte estratégia para desenvolver este star-schema:

| **Tabela** | **Tipo** |
|--------|------|
| Disciplinas Ministradas | Fato |
| Curso | Dimensão |
| Disciplina | Dimensão |
| Departamento | Dimensão |
| Tempo | Dimensão |
| Professor | Dimensão |

## Conclusão

Essas perguntas ajudam a definir quais fatos e dimensões devem ser levados em consideração para construir o modelo dimensional centrado nos professores. Utilizamos a mesma ferramenta para desenvolver o star-schema, e apresentamos o diagrama analítico aqui: [star-schema_professor](./diagrama_relacionamento_dimensional.png).
