# coding-project-template
Parte 1 – Criando o Hook UseFetch.jsx

“Vamos começar criando um custom hook chamado useFetch. A ideia desse hook é ter um lugar centralizado para buscar dados de qualquer API, sem precisar repetir a mesma lógica toda vez em cada componente.

Primeiro, importamos o React e dois hooks importantes: useState e useEffect. O useState vai guardar os dados que chegarem da API, e o useEffect vai controlar quando a busca vai acontecer.

Em seguida, criamos a função useFetch, que recebe uma URL como parâmetro. Essa URL é o endereço da API que queremos consultar.

Dentro da função, criamos o estado data e a função setData. O data vai armazenar os dados que vierem da API, e o setData é o que usamos para atualizar esse estado quando os dados chegarem.

Agora usamos o useEffect. Ele verifica se a URL existe, e então faz a requisição usando fetch. Quando a resposta chega, transformamos em JSON e guardamos no estado data. Caso haja algum erro na requisição, registramos o erro no console e limpamos o estado, para evitar problemas.

Por fim, retornamos o data dentro de um array, para que qualquer componente que usar esse hook consiga desestruturar e pegar apenas os dados. E, claro, exportamos o hook para ser usado em outros arquivos.

Com isso, criamos um hook genérico, reutilizável, que pode buscar dados de qualquer URL de forma segura e limpa.”

Parte 2 – Criando o componente FetchYogaData.jsx

“Agora vamos criar um componente chamado FetchYogaData. Esse componente vai usar o hook que acabamos de criar para buscar dados de uma API de Yoga.

Primeiro, importamos o React, nosso hook UseFetch e o arquivo de estilos CSS. O CSS vai nos permitir estilizar a lista de forma organizada.

Dentro do componente, chamamos UseFetch passando a URL da API de Yoga. O hook retorna os dados, que colocamos na variável data. Para garantir que está funcionando, fazemos um console.log de data.

No retorno do componente, construímos uma lista. Colocamos um título dizendo “Yoga Benefits” e depois percorremos cada item de data. Para cada elemento, mostramos o nome do exercício de Yoga, os benefícios e a duração da prática.

Esse componente está totalmente dependente do UseFetch, pois ele não sabe buscar os dados sozinho. Ele apenas consome os dados que o hook retorna e os apresenta na tela de forma organizada.”

Parte 3 – Criando o arquivo Fruit.json

“Agora temos um arquivo de dados chamado Fruit.json. Esse arquivo é apenas um banco de dados local em formato JSON, com informações sobre frutas e alimentos.

Cada objeto dentro do array tem o nome da fruta, a URL de uma imagem, os benefícios, a importância nutricional e o melhor horário para consumo.

O propósito desse arquivo é simular uma API local, ou fornecer dados estáticos que podem ser usados diretamente no componente, sem precisar fazer uma requisição externa.”

Parte 4 – Criando o componente FetchData.jsx

“Finalmente, criamos o componente FetchData. Esse componente vai mostrar os dados do Fruit.json na tela.

Primeiro, importamos o React, o JSON com os dados e o CSS de estilos.

Dentro do componente, atribuímos os dados do JSON à variável data. Diferente do FetchYogaData, aqui não precisamos de fetch, porque os dados já estão localmente no arquivo.

No retorno, colocamos um título que indica que estamos mostrando dados de frutas. Em seguida, criamos uma lista e percorremos cada elemento de data. Para cada fruta, mostramos o nome, a imagem, os benefícios, a importância nutricional e o melhor horário para consumir.

Esse componente funciona de forma independente do hook UseFetch, mas a lógica de percorrer dados e exibi-los na tela é a mesma que usamos no FetchYogaData. Se quisermos, poderíamos até adaptar o FetchData para usar UseFetch e buscar os dados de uma API externa, tornando os dois componentes consistentes.”

Como tudo se interliga

O UseFetch é o cérebro que busca dados de qualquer API.

O FetchYogaData é um exemplo de componente que consome dados externos via UseFetch.

O Fruit.json é um banco de dados local, útil para testes ou dados estáticos.

O FetchData consome esses dados estáticos e os mostra na tela, usando a mesma lógica de renderização que o FetchYogaData.
