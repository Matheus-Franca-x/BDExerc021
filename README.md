# BDExerc021
## SQLWork.sql
### Considere o diagrama abaixo:

![image](https://github.com/Matheus-Franca-x/BDExerc021/assets/99504777/e6c12127-4eca-4945-831e-1b63564bfb43)

### Criar as tabelas da forma que foram diagramadas, obedecendo as seguintes restrições:
-A coluna users_id da tabela associativa é FK da coluna id, tabela users.
-A coluna projects_id da tabela associativa é FK da coluna id, tabela projects.
-A coluna date da tabela projects deve verificar se a data é posterior que 01/09/2014.
-Caso contrário, o registro não deve ser inserido.
-A PK de projects deve ser de auto incremento, iniciando em 10001, com incremento de 1.
-A PK de users deve ser de auto incremento, iniciando em 1, com incremento de 1.
-O valor padrão da coluna password da tabela users, deverá ser 123mudar.
-A coluna username da tabela users deve ter restrição de unicidade.

### Modificações:
-Modificar a coluna username da tabela Users para varchar(10)
-Modificar a coluna password da tabela Users para varchar(8)

### Inserir os dados abaixo:
#### users:
| Id | Name | Username | Password | Email |
| - | --------- | ---------- | -------- | --------------------- |
| 1 | Maria     | Rh_maria   | 123mudar | maria@empresa.com     |
| 2 | Paulo     | Ti_paulo   | 123@456  | paulo@empresa.com     |
| 3 | Ana       | Rh_ana     | 123mudar | ana@empresa.com       |
| 4 | Clara     | Ti_clara   | 123mudar | clara@empresa.com     |
| 5 | Aparecido | Rh_apareci | 55@!cido | aparecido@empresa.com |

#### projects:
|   Id   |      Name       |          Description          |    Date    |
|--------|-----------------|-------------------------------|------------|
| 10001  | Re-folha        | Refatoração das Folhas        | 05/09/2014 |
| 10002  | Manutenção PC's | Manutenção PC's               | 06/09/2014 |
| 10003  | Auditoria       | NULL                          | 07/09/2014 |

#### users_projects:
| Users_id | Projects_id |
|----------|-------------|
|    1     |   10001     |
|    5     |   10001     |
|    3     |   10003     |
|    4     |   10002     |
|    2     |   10002     |

### Considerar as situações:
- O projeto de Manutenção atrasou, mudar a data para 12/09/2014.
- O username de aparecido (usar o nome como condição de mudança) está feio, mudar para Rh_cido.
- Mudar o password do username Rh_maria (usar o username como condição de mudança) para 888@*, mas a condição deve verificar se o password dela ainda é 123mudar.
- O user de id 2 não participa mais do projeto 10002, removê-lo da associativa.

## SQLLocadora.sql
### Considere o diagrama abaixo:

![image](https://github.com/Matheus-Franca-x/BDExerc021/assets/99504777/7e0d7ff0-ad86-4f1c-b368-bf4e62943652)

### Restrições:
-Ano de filme deve ser menor ou igual a 2021.
-Data de fabricação de DVD deve ser menor do que hoje.
-Número do endereço de Cliente deve ser positivo.
-CEP do endereço de Cliente deve ter, especificamente, 8 caracteres.
-Data de locação de Locação, por padrão, deve ser hoje.
-Data de devolução de Locação, deve ser maior que a data de locação.
-Valor de Locação deve ser positivo.

### Esquema:
-A entidade estrela deveria ter o nome real da estrela, com 50 caracteres
-Verificando um dos nomes de filme, percebeu-se que o nome do filme deveria ser um atributo com 80 caracteres

### Considere os dados:
#### filme:
|   ID   |                             Filme                           |  Ano  |
|--------|-------------------------------------------------------------|-------|
|  1001  | Whiplash                                                    | 2015  |
|  1002  | Birdman                                                     | 2015  |
|  1003  | Interestelar                                                | 2014  |
|  1004  | A Culpa é das Estrelas                                      | 2014  |
|  1005  | Alexandre e o Dia Terrível, Horrível, Espantoso e Horroroso | 2014  |
|  1006  | Sing                                                        | 2016  |

#### estrela:
|   ID   |      Nome       |        Nome Real     |
|--------|-----------------|----------------------|
|  9901  | Michael Keaton  | Michael John Douglas |
|  9902  | Emma Stone      | Emily Jean Stone     |
|  9903  | Miles Teller    | NULL                 |
|  9904  | Steve Carell    | Steven John Carell   |
|  9905  | Jennifer Garner | Jennifer Anne Garner |

#### filme_estrela:
|filme_estrela|
| FilmeId | EstrelaId |
|---------|-----------|
|  1002   |   9901    |
|  1002   |   9902    |
|  1001   |   9903    |
|  1005   |   9904    |
|  1005   |   9905    |

#### dvd:

