# React Native - Image Picker

## Hybrid Mobile App Development

## Image Picker

Já aprendemos sobre como utilizar a câmera do nosso celular para tirar uma foto,
ou até mesmo utilizar ela em real time, agora, veremos como podemos fazer para
utilizar as fotos que estão em nossa galeria.
Para isso criaremos um aplicativo que fará um reconhecimento da imagem que
estamos pegando da nossa biblioteca.

## Código do Exemplo

Para que possamos iniciar o nosso projeto e não precisarmos codar tudo do
começo, irei deixar uma parte pronta para que possamos ir direto ao ponto.
Para isso, vou deixar o link do github, que devemos clonar e utiliza-lá a partir da
master:
https://github.com/victorb132/image-recognize.git

Após o projeto clonado, podemos instalar 3 bibliotecas que nos ajudará nesse
caminho:
npx expo install expo-image-picker
npx expo install expo-image-manipulator
npm install axios
Com esse comando devemos ter três bibliotecas instaladas:

1. expo-image-picker: que nos entrega as funções de pegar as imagens da câmera
2. expo-image-manipulator: que nos permite editar melhor a imagem
3. axios: para fazer a chamada para nossa api de IA.

Após ter feito clone, teremos a seguinte estrutura e a seguinte tela:

![Capture](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/52076e32-3ec7-4ca3-927a-bc048d5936d3) ![Capture2](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/0b3ae243-c995-4826-a1c3-de035074bf0d)

Dentro do index da Home teremos todo esse código:

![Capture3](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/6a398c7c-9fad-43a5-ae35-2a039dabee67)   ![Capture](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/9770a39d-1c65-41b6-9ee6-74f95913766d)

Nossa Home, trás uma estrutura pré-pronta, importando alguns componentes que
poderemos reutilizar em todo nosso app se quisermos, trás também a função
handleSelectImage que preencheremos e fará a abertura do nosso Image Picker e
poderemos selecionar e controlar a imagem que será selecionada.
E por fim, trazemos nossa árvore de elementos que faz nossa página inicial e
renderiza tudo.

Antes de continuar no código, podemos criar nosso projeto no Clarifai.
E o que é o Clarifai? O Clarifai é uma I.A com diversas funções gratuitas, e iremos
utilizar desse serviço o de reconhecimento de imagem que a partir da nossa imagem irá
trazer o que tem nessa imagem de informação, para isso, devemos seguir alguns
passos.

![Capture4](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/4232bb6d-62ac-4623-b287-148b71bf7b53)

1. Devemos entrar no site do Clarifai:
https://www.clarifai.com/
2. Devemos nos logar, para isso podemos escolher nos cadastrar e entrar com Github,
Google ou até mesmo criar uma usuário direto
3. Depois de logados teremos uma área para criar um aplicativo podemos fazer isso
clicando em + Create.

![Capture5](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/7f892fdd-0b54-40b3-91cb-5af6a99bbb70)

4. Escolhemos "Start with a blank app" e colocamos um App Id único ( Aqui pode ser o
nome do seu aplicativo ), deixamos do jeito que está e clicamos em Create App:

![Capture6](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/2fb8d657-a17f-4330-8991-f104b5665deb)

5. Abrimos nosso projeto e clicamos em Models e depois Add Model:

![Capture7](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/d1f5c6a6-e725-4168-9ff6-28f64a63d9b3)

6. Escolhemos a opção Pre-trained Model (Community):

![Capture8](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/bad091c0-1341-4f09-8d0b-3d3e2d70036a)

7. Depois podemos escolher Image Recognition:

![Capture9](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/cd1401fd-8793-4469-b661-7dbc00c5dcf2)

8. Nesa tela, devemos pegar algumas informações e salvar, que é o token ao lado do
"See versions table":

![Capture10](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/0abec5c5-6887-41bf-8b37-3eeb13362e3e)

9. Com isso salvo podemos voltar para nosso código.

Agora faremos alguns tratamentos dentro da nossa função handleSelectImage, como a
seguir:

![Capture11](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/78344233-f028-45ed-b490-f1bb72fa9e36)

Criaremos também uma nova função para detectar nossa imagem e enviar parar o
Clarifai e receber um retorno da api deles:

![Capture12](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/1d90171e-d034-4b45-9011-c91edb850d96)

E feito isso podemos alterar algumas coisas na nossa árvore de elementos:

![Capture13](https://github.com/jvsobraz/ImagePicker-FIAP/assets/100175547/db9aa5fd-cb3f-4188-851b-0b6996b84f04)
