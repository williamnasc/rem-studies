# Explorando o Sionna RT e Blender

Compilado de dicas e links para ajudar no aprendizado do Sionna e a preparação de cenários usando o blender.

## Requisitos de software

O Sionna RT é a parte do simulador da nvidia que utiliza de estratégias de Ray Tracing para os cálculos de propagação de ondas para que seja possível utilizar esse recurso do Sionna e necessário que a GPU utilizada tenha suporte ao CUDA da nvidia.

É possível rodar o Sionna RT utilizando CPU desde que você instale o LLVM do Dr.Jit como apresentado no [tutorial de instalação oficial](https://nvlabs.github.io/sionna/installation.html)

- Requisitos para o Sionna
  - Python 3.10-3.12
  - TensorFlow 2.14-2.19
    ```python
    pip install tensorflow==2.19.0
    ```
  - Mitsuba
    ```python
    pip install mitsuba
    ```
  - LLVM e Dr.Jit
    - Linux
      ```python
      sudo apt install llvm
      ```
    - Windows
      - Instalador no [link](https://drjit.readthedocs.io/en/latest/what.html#backends).

Para montar os cenários é possível utilizar o Blender e alguns plugins para facilitar a obtenção de modelos 3d a partir de mapas e para converter o arquivo do blender para o formato aceito pelo Sionna (Mitsuba 3)

## Montar ambiente do Sionna

- INSTALA O LLVM PARA PODER INSTALAR O SIONA EM CUDA (INCONSISTENTE)
sudo apt install llvm

- CRIA UMA VENV PARA INSTALAR O SIONNA
python3 -m venv venv
source venv/bin/activate

- INSTALA O SIONNA
pip install sionna

## Como configurar o Blender para Gerar o arquivo para o Sionna

Após instalar Blender, é necessário adicionar um pluguin para que ele seja capaz de exportar o projeto no formato mitsuba.

O repositório para download com o tutorial de instalação plugin no blender está disponível [neste link](https://github.com/mitsuba-renderer/mitsuba-blender).

- TODO : montar cenario (configurar todos os params, adicionar os tipos de mateiral)
- TODO : exportar o xml

É comum que o plugin do mitsuba não consiga instalar corretamente as dependências e não aparece a opção de exportar no formato mitsuba. Para rodar o Sionna evitando o erro do Mitsuba use o comando: 

.\blender.exe --python-use-system-env

## TODO: Montagem do cenário de simulação no Blender

para montar o cenário no Blender e exportar corretamente é necessário se atentar a alguns detalhes. Existe um tutorial da própria NVIDIA que ensina e exemplifica esse processo. 

[link do tutorial](https://www.youtube.com/watch?v=7xHLDxUaQ7c)

## Como acessar o jupyter notebook do LANCE com sionna

No LANCE temos um servidor com um jupyter notebook com o sionna instalado para facilitar o acesso e permitir o uso de maior processamento computacional caso seja necessário.

Para acessar esse serviço basta estar na rede do LANCE ou conectado a VPN e acessar um os seguintes links:

  - [Serviço padrão](http://172.31.0.41:8888/?token=600b6a71154f38b5b8a8a43dfcd24eb341b5ef897668104b)
  - [Serviço de teste do sionna](http://172.31.0.41:9999/)