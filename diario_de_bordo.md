# Diário de Bordo

## Biblioteca Go para construir servidores GraphQL
https://gqlgen.com/getting-started/

```
# Criar módulo
$ go mod init <nomeModulo>
```
Criar o arquivo tools.go

```
# Baixar todas as dependências
$ go mod tidy
```
```
# Gerar a estrutura do graphql
$ go run github.com/99designs/gqlgen init
```
```
# Subir o servidor graphql
$ go run server.go
```
```
# Gerar a estrutura da aplicação com base no schema graphql
$ go run github.com/99designs/gqlgen generate
```

## SQL das tabelas
Acessar o sqlite no terminal do container da aplicação

```
sqlite3 data.db

create table categories (id string, name string, description string);
create table courses (id string, name string, description string, category_id string);

#Estrutura da tabela
.schem <NomeTabela>

#Estrutura das tabelas
.schema

# Para sair
.exit
```

## Query e mutation
```
mutation createCategory{
  createCategory(input:{
    name: "Tecnologia",
    description: "Cursos de Tecnologia"
  }){
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(input: {name: "Full Cycle", description: "The Best", categoryId: ""}){
    id
    name
  }
}

query queryCategories{
  categories {
    id
    name
  }
}

query queryCategoriesWithCourses{
  categories {
    id
    name
    courses{
      id
      name
    }
  }
}

query queryCourses{
  courses{
    id
    name
  }
}

query queryCoursesWithCategory{
  courses{
    id
    name
    category{
      id
      name
      description
    }
  }
}
```
