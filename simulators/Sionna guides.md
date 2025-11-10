# Explorando o Sionna RT e Blender

Compilado de dicas e links para ajudar no aprendizado do Sionna e a preparação de cenários usando o blender.

## Requisitos de software

O Sionna RT é a parte do simulador da nvidia que utiliza de estratégias de Ray Tracing para os cálculos de propagação de ondas para que seja possível utilizar esse recurso do Sionna e necessário que a GPU utilizada tenha suporte ao CUDA da nvidia.

É possível rodar o Sionna RT utilizando CPU desde que você instale o LLVM do Dr.Jit como apresentado no [tutorial de instalação oficial](https://nvlabs.github.io/sionna/installation.html)

- Requisitos para o Sionna
  - Python 3.10-3.12
  - TensorFlow 2.14-2.19
  - Mitsuba
  - LLVM e Dr.Jit

Para montar os cenários é possível utilizar o Blender e alguns plugins para facilitar a obtenção de modelos 3d a partir de mapas e para converter o arquivo do blender para o formato aceito pelo Sionna (Mitsuba 3)


Para rodar o Sionna evitando o erro do Mitsuba use o comando: .\blender.exe --python-use-system-env

- INSTALA O LLVM PARA PODER INSTALAR O SIONA EM CUDA (INCONSISTENTE)
sudo apt install llvm

- CRIA UMA VENV PARA INSTALAR O SIONNA
python3 -m venv venv
source venv/bin/activate

- INSTALA O SIONNA
pip install sionna

## Como configurar o Blender para Gerar o arquivo para o Sionna

- instalar plugin do blender
- montar cenario (configurar todos os params, adicionar os tipos de mateiral)
- exportar o xml

## Como acessar o jupyter notebook do LANCE com sionna

- estar na rede ou na VPN
- links
  - servidor padrão: http://172.31.0.41:8888/?token=600b6a71154f38b5b8a8a43dfcd24eb341b5ef897668104b
  - servidor de teste do sionna : http://172.31.0.41:9999/