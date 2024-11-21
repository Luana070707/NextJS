# SuperHeroe - NextJS

## Descrição do Projeto
Este projeto tem como objetivo reconstruir a aplicação SuperHeroe utilizando o framework Next.js. A aplicação exibe um conjunto de super-heróis e suas características (como inteligência e força) a partir de uma API de super-heróis.

## Funcionalidades 
- Exibe uma lista de super-heróis, com imagem e estatísticas de inteligência e força.
- Utiliza a API pública SuperHeroAPI para buscar os dados dos super-heróis.
- A interface da aplicação é feita com Next.js e React.
- As cores da aplicação foram modificadas para utilizar tons de roxo e azul.

## Tecnologias Utilizadas
- Next.js: Framework React para renderização do lado do servidor e criação de páginas dinâmicas.
- React: Biblioteca para construir interfaces de usuário.
- CSS: Para estilização da interface.

# Passo a Passo da Implementação

## 1. Criação do Projeto Next.js
  Para iniciar, criamos um novo projeto Next.js com o comando:

```
  npx create-next-app@latest superhero-nextjs
```
Isso criou a estrutura básica do projeto, incluindo todos os arquivos necessários para começar.

## 2. Instalação de Dependências
Após criar o projeto, navegamos até o diretório do projeto:

```
cd superhero-nextjs
```

Em seguida, instalamos as dependências necessárias (como o Next.js) e iniciamos o servidor de desenvolvimento:

```
npm run dev
```

## 3. Configuração do Código no pages/index.js
Dentro do arquivo pages/index.js, implementamos a lógica para buscar e exibir os dados dos super-heróis.

- Estrutura do arquivo index.js:

```
import { useEffect, useState } from 'react';

export default function Home() {
  const [heroes, setHeroes] = useState([]);

  useEffect(() => {
    // Chama a função para buscar os heróis
    fetchHeroes();
  }, []);

  // Função para buscar os heróis da API
  const fetchHeroes = async () => {
    const HEROES_IDS = [1, 2, 3, 4, 5]; // IDs dos heróis que vamos buscar
    const results = [];

    for (let id of HEROES_IDS) {
      const response = await fetch(`https://superheroapi.com/api.php/YOUR_ACCESS_TOKEN/${id}`);
      const data = await response.json();
      results.push(data);
    }

    setHeroes(results); // Atualiza o estado com os heróis
  };

  return (
    <div id="heroes">
      {heroes.map(hero => (
        <article key={hero.id}>
          <img src={hero.image.url} alt={hero.name} />
          <h1>{hero.name}</h1>
          <p>Intelligence: <span style={{ width: `${hero.powerstats.intelligence}%`, backgroundColor: '#F9B32F' }}></span></p>
          <p>Strength: <span style={{ width: `${hero.powerstats.strength}%`, backgroundColor: '#FF7C6C' }}></span></p>
        </article>
      ))}
    </div>
  );
}
```

- ATENÇÃO: Substitua YOUR_ACCESS_TOKEN pelo token gerado por você na `SuperHeroAPI`.

## 4. Estilização do Projeto
Modificamos o estilo CSS para criar uma interface limpa e visualmente agradável, com o uso de cores roxas e azuis. Abaixo está o código CSS:

```
#heroes {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
}

#heroes article {
  width: 300px;
  background-color: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

#heroes article img {
  width: 100%;
  height: auto;
}

#heroes article h1 {
  text-align: center;
  margin: 10px 0;
}

#heroes article p {
  padding: 0 10px;
}

#heroes article span {
  display: block;
  height: 10px;
  border-radius: 5px;
}
```
As cores e a disposição foram personalizadas para criar uma visualização atrativa dos super-heróis.

## 5. Como Rodar o Projeto
Para rodar o projeto localmente, siga os seguintes passos:
- 1- Clone ou baixe o repositório do projeto.
- 2- Navegue até o diretório do projeto.
- 3- execute esse comando no terminal:
 
```
cd superhero-nextjs
```

- 4- Instale as dependências:

```
npm install

```

- 5- Inicie o servidor de desenvolvimento:
 

```
npm run dev
```

A sua rederização irá rodas aqui: `http://localhost:3000`

## 6. Visualização

Ao acessar a aplicação em `http://localhost:3000`, você verá a lista de super-heróis, com seus nomes, imagens e as barras de inteligência e força, de acordo com os dados recuperados da API.

## 7. Conclusão
Este projeto foi reconstruído utilizando Next.js e exibe de forma dinâmica uma lista de super-heróis. Ele utiliza a API do SuperHeroAPI para buscar os dados de heróis específicos, e os exibe de forma interativa e bem estilizada.

## Abaixo você encontra uma imagem rodando no servidor local:

 ![js](https://github.com/user-attachments/assets/0d0690f8-a975-4f6b-98f3-c1fdc3946ecd)











 






  
  
