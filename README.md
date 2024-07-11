# Praticando SQL Curso Proz...

Lembre-se, cada desafio é uma chance de crescer. Não se desanime com os erros; eles são degraus no caminho do aprendizado. E acima de tudo, divirta-se! 
O aprendizado mais eficaz acontece quando nos engajamos e nos interessamos pelo que estamos fazendo.

#### Desafios - Respostas
```
Entidade Estudante
1-Atributo Simples: DataNascimento (data de nascimento do estudante).
2-Atributo Composto: Nome (composto por PrimeiroNome e Sobrenome).
3-Atributo Multivalorado: Telefones (o estudante pode ter mais de um número de telefone).
```

Representação da Entidade Estudante
```

Estudante

ID (Chave Primária)
Nome
    - PrimeiroNome
    - Sobrenome
DataNascimento
Telefones (Multivalorado)
```

Descrição dos Atributos
```

ID: Identificador único do estudante (chave primária).
Nome: Atributo composto que inclui PrimeiroNome e Sobrenome.
PrimeiroNome: Primeiro nome do estudante.
Sobrenome: Sobrenome do estudante.
DataNascimento: Data de nascimento do estudante.
Telefones: Atributo multivalorado que pode incluir vários números de telefone para o estudante.
```

Modelo Conceitual (Diagrama ER)
```

Um diagrama de entidade-relacionamento (ER) poderia ser representado da seguinte forma:
```

+---------------+
|   Estudante   |
+---------------+
| ID            |
| Nome          |
|- PrimeiroNome |
|   - Sobrenome |
| DataNascimento|
| Telefones     |
+---------------+
```
Convertendo para SQL...
Para converter essa entidade para SQL, precisaríamos criar duas tabelas: uma para Estudante e outra para os Telefones associados a cada estudante.
---

```sql
-- Criar a tabela Estudante
CREATE TABLE Estudante (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    PrimeiroNome VARCHAR(50),
    Sobrenome VARCHAR(50),
    DataNascimento DATE
);

-- Criar a tabela Telefones
CREATE TABLE Telefones (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    EstudanteID INT,
    Telefone VARCHAR(15),
    FOREIGN KEY (EstudanteID) REFERENCES Estudante(ID)
);
```
Descrição das Tabelas SQL
Tabela Estudante:

ID: Chave primária para identificar cada estudante.
PrimeiroNome: Primeiro nome do estudante.
Sobrenome: Sobrenome do estudante.
DataNascimento: Data de nascimento do estudante.
Tabela Telefones:

ID: Chave primária para identificar cada número de telefone.
EstudanteID: Chave estrangeira que referencia o ID da tabela Estudante.
Telefone: Número de telefone do estudante.
Esse modelo permite que cada estudante tenha um ou mais números de telefone associados, respeitando a estrutura de atributos simples, compostos e multivalorados.
```

