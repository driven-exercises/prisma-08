# prisma-08: Estudantes Empregados

- Assim como no SQL, podemos fazer uso da API do Prisma para trazer as informações presentes no banco de dados das mais diferentes maneiras possíveis.
- ➡️ O que fazer?
    - Para este exercício, é necessário executar o seed para popular o banco. Não deve demorar mais do que alguns segundos.
    - No arquivo index.ts, construa uma lógica capaz de entregar as informações solicitadas por cada um dos requisitos abaixo - um por vez:
        1. Agrupamento de alunos por turma (quantos alunos tem cada turma?).
            
            ```sql
            SELECT COUNT(id), "class" FROM students s
            GROUP BY "class"
            ORDER BY COUNT(id) desc;
            ```
            
        2. Agrupamento de alunos por turma que ainda não tem trabalho (quantos alunos em cada turma ainda não se empregaram?)
            
            ```sql
            SELECT COUNT(*), s."class" FROM students s
            WHERE s."jobId" is null
            GROUP BY s."class"
            ORDER BY COUNT(*) desc
            ```
