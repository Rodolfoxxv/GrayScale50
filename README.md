# GrayScale50 Transforma a Exibição de Imagens PPM

Este repositório contém funções para transformar imagens no formato PPM e exibi-las de várias maneiras no terminal, incluindo conversão para escala de cinza, binarização e exibição de imagens em 50 tons de cinza.

---

## Funcionalidades

1. **Converter para Escala de Cinza**:
   - A função `mostrar_imagem_cinza` converte uma imagem PPM para escala de cinza, utilizando a fórmula de luminância:
   
     ```
     Cinza = 0.299 * R + 0.587 * G + 0.114 * B
     ```
   - A imagem convertida é exibida no terminal usando o mapa de cores `gray` com intensidade variando de 0 (preto) a 255 (branco).

2. **Converter para Binário (Preto e Branco)**:
   - A função `mostrar_imagem_binaria` converte a imagem para binário, utilizando um limiar para separar os pixels em preto (0) ou branco (255). O padrão de limiar é 128, mas pode ser ajustado conforme necessário.

3. **Exibição Comparativa**:
   - A função `mostrar_imagem` permite visualizar a imagem original, sua versão em escala de cinza e sua versão binarizada, tudo em uma única tela.

4. **Exibição com Quadrados**:
   - A função `mostrar_imagem_com_quadrados` exibe a imagem com a adição de quadrados ao redor de cada pixel, permitindo uma visualização mais detalhada da imagem.

5. **Exibição no Terminal com 50 Tons de Cinza**:
   - A função `exibir_imagem_terminal` exibe a imagem com 50 tons de cinza diretamente no terminal, mantendo as versões em preto e branco.

---

## Como Usar

### 1. Instalação das Dependências

Você precisará de Python e das bibliotecas `numpy` e `matplotlib` para processar e exibir as imagens. Para instalar as dependências, use o comando:

```bash
pip install numpy matplotlib
2. Carregar e Processar a Imagem
As funções podem ser usadas para carregar e processar imagens PPM, que devem estar no formato P3 (texto). As funções esperam que a imagem tenha um valor máximo de cor de 255.

Exemplo de uso:
python
Sempre exibir os detalhes

Copiar código
caminho = 'imagem.ppm'  # Caminho para a sua imagem PPM

# Exibir imagem em escala de cinza
mostrar_imagem_cinza(caminho)

# Exibir imagem binária
mostrar_imagem_binaria(caminho)

# Exibir comparativo entre a imagem original, em escala de cinza e binarizada
mostrar_imagem(caminho)

# Exibir imagem com quadrados ao redor dos pixels
mostrar_imagem_com_quadrados(caminho)

# Exibir imagem no terminal com 50 tons de cinza
largura, altura, pixels = ler_imagem_ppm(caminho)
imagem_cinza = converter_para_cinza(largura, altura, pixels)
imagem_binaria = binarizar_imagem(largura, altura, imagem_cinza)
escala = 0.05  # Reduz a imagem para 5% do tamanho original

# Exibir imagem reduzida em 50 tons de cinza
nova_largura, nova_altura, imagem_reduzida_cinza = reduzir_imagem(largura, altura, imagem_cinza, escala)
exibir_imagem_terminal(nova_largura, nova_altura, imagem_reduzida_cinza)

# Exibir imagem binária reduzida
nova_largura_bin, nova_altura_bin, imagem_reduzida_binaria = reduzir_imagem(largura, altura, imagem_binaria, escala)
exibir_imagem_terminal(nova_largura_bin, nova_altura_bin, imagem_reduzida_binaria)
Funções Principais
mostrar_imagem_cinza(caminho_arquivo)
Converte a imagem PPM para escala de cinza e a exibe no terminal.

mostrar_imagem_binaria(caminho_arquivo, limiar=128)
Converte a imagem PPM para binário e a exibe no terminal. O valor de limiar pode ser ajustado para alterar a definição do ponto de corte entre preto e branco.

mostrar_imagem(caminho_arquivo, limiar=128, grid_size=10)
Exibe a imagem original, em escala de cinza e binarizada lado a lado em uma única tela, com a opção de adicionar uma grade.

mostrar_imagem_com_quadrados(caminho_arquivo, limiar=128, grid_size=10)
Exibe a imagem com quadrados ao redor de cada pixel, proporcionando uma visualização detalhada da composição da imagem.

ler_imagem_ppm(caminho_arquivo)
Lê uma imagem PPM e retorna os dados de pixels (R, G, B).

converter_para_cinza(largura, altura, pixels)
Converte os pixels de uma imagem para escala de cinza.

binarizar_imagem(largura, altura, imagem_cinza, limiar=128)
Converte a imagem em escala de cinza para uma versão binária (0 ou 255).

reduzir_imagem(largura, altura, imagem, escala=0.1)
Reduz o tamanho da imagem mantendo a escala de cinza ou binária.

exibir_imagem_terminal(largura, altura, imagem)
Exibe a imagem no terminal com 50 tons de cinza, mantendo o preto e branco.

Exemplo de Saída
Após executar o código, você verá a seguinte saída (dependendo da função que você escolher):

Imagem em Escala de Cinza: A imagem será exibida em tons de cinza.
Imagem Binária: A imagem será convertida em preto e branco com base no limiar definido.
Comparativo: A imagem original, em escala de cinza e binarizada serão exibidas lado a lado.
Imagem com Quadrados: Cada pixel será demarcado com um quadrado, facilitando a visualização.
Imagem no Terminal: A imagem será exibida diretamente no terminal com 50 tons de cinza e preto e branco.
Observações
As imagens devem estar no formato PPM (P3), com valores RGB entre 0 e 255.
As funções de exibição no terminal utilizam os códigos ANSI para cores e podem ser limitadas pelo terminal em uso. """





