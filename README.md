<p align="center">
    <a href="https://github.com/3b1b/manim">
        <img src="https://raw.githubusercontent.com/3b1b/manim/master/logo/cropped.png">
    </a>
</p>

[![versão pypi](https://img.shields.io/pypi/v/manimgl?logo=pypi)](https://pypi.org/project/manimgl/)
[![Licença MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](http://choosealicense.com/licenses/mit/)
[![Manim Subreddit](https://img.shields.io/reddit/subreddit-subscribers/manim.svg?color=ff4301&label=reddit&logo=reddit)](https://www.reddit.com/r/manim /)
[![Manim Discord](https://img.shields.io/discord/581738731934056449.svg?label=discord&logo=discord)](https://discord.com/invite/bYCyhM9Kz2)
[![docs](https://github.com/3b1b/manim/workflows/docs/badge.svg)](https://3b1b.github.io/manim/)

Manim é um mecanismo para animações programáticas precisas, projetado para criar vídeos explicativos de matemática.

Observe que existem duas versões do manim. Este repositório começou como um projeto pessoal do autor de [3Blue1Brown](https://www.3blue1brown.com/) com o objetivo de animar esses vídeos, com código específico de vídeo disponível [aqui](https://github. com/3b1b/vídeos). Em 2020, um grupo de desenvolvedores o dividiu no que agora é a [edição da comunidade](https://github.com/ManimCommunity/manim/), com o objetivo de ser mais estável, melhor testado, mais rápido para responder às contribuições da comunidade, e mais amigável para começar. Consulte [esta página](https://docs.manim.community/en/stable/faq/installation.html#different-versions) para obter mais detalhes.

## Instalação
> **AVISO:** Estas instruções são para ManimGL _somente_. Tentar usar estas instruções para instalar [ManimCommunity/manim](https://github.com/ManimCommunity/manim) ou as instruções lá para instalar esta versão causará problemas. Você deve primeiro decidir qual versão deseja instalar e seguir apenas as instruções para a versão desejada.
>
> **Nota**: Para instalar o manim diretamente pelo pip, preste atenção ao nome do pacote instalado. Este repositório é o ManimGL de 3b1b. O nome do pacote é `manimgl` em vez de `manim` ou `manimlib`. Por favor, use `pip install manimgl` para instalar a versão neste repositório.

Manim é executado em Python 3.7 ou superior.

Os requisitos do sistema são [FFmpeg](https://ffmpeg.org/), [OpenGL](https://www.opengl.org/) e [LaTeX](https://www.latex-project.org) ( opcional, se você quiser usar o LaTeX).
Para Linux, [Pango](https://pango.gnome.org) junto com seus cabeçalhos de desenvolvimento são necessários. Veja as instruções [aqui](https://github.com/ManimCommunity/ManimPango#building).


### Diretamente

```sh
# Instale o manimgl
pip instalar manimgl

# Experimente
manimgl
```

Para mais opções, dê uma olhada nas seções [Using manim](#using-manim) abaixo.

Se você quiser hackear o próprio manimlib, clone este repositório e nesse diretório execute:

```sh
# Instale o manimgl
pip instalar -e .

# Experimente
manimgl example_scenes.py OpeningManimExample
# ou
manim-render example_scenes.py OpeningManimExample
```

### Diretamente (Windows)

1. [Instale o FFmpeg](https://www.wikihow.com/Install-FFmpeg-on-Windows).
2. Instale uma distribuição LaTeX. [MiKTeX](https://miktex.org/download) é recomendado.
3. Instale os pacotes restantes do Python.
    ```sh
    git clone https://github.com/3b1b/manim.git
    cd manim
    pip instalar -e .
    manimgl example_scenes.py OpeningManimExample
    ```

### Mac OS X

1. Instale FFmpeg, LaTeX no terminal usando homebrew.
    ```sh
    preparar instalar ffmpeg mactex
    ```
   
2. Instale a versão mais recente do manim usando estes comandos.
    ```sh
    git clone https://github.com/3b1b/manim.git
    cd manim
    pip instalar -e .
    manimgl example_scenes.py OpeningManimExample
    ```

## Instalação do Anaconda

1. Instale o LaTeX como acima.
2. Crie um ambiente conda usando `conda create -n manim python=3.8`.
3. Ative o ambiente usando `conda activate manim`.
4. Instale o manimgl usando `pip install -e .`.


## Usando manim
Tente executar o seguinte:
```sh
manimgl example_scenes.py OpeningManimExample
```
Isso deve abrir uma janela reproduzindo uma cena simples.

Alguns sinalizadores úteis incluem:
* `-w` para gravar a cena em um arquivo
* `-o` para gravar a cena em um arquivo e abrir o resultado
* `-s` para pular para o final e mostrar apenas o quadro final.
    * `-so` salvará o quadro final em uma imagem e o mostrará
* `-n <número>` para pular para a `n`'ésima animação de uma cena.
* `-f` para tornar a janela de reprodução em tela cheia

Dê uma olhada em custom_config.yml para mais configurações. Para adicionar sua personalização, você pode editar este arquivo ou adicionar outro arquivo com o mesmo nome "custom_config.yml" em qualquer diretório a partir do qual você esteja executando o manim. Por exemplo [este é o único](https://github.com/3b1b/videos/blob/master/custom_config.yml) para vídeos 3blue1brown. Lá você pode especificar para onde os vídeos devem ser enviados, onde o manim deve procurar arquivos de imagem e sons que deseja ler e outros padrões em relação ao estilo e qualidade do vídeo.

Veja as [cenas de exemplo](https://3b1b.github.io/manim/getting_started/example_scenes.html) para ter uma noção de como é usado e sinta-se à vontade para examinar o código por trás dos [3blue1brown videos]( https://github.com/3b1b/videos) para um conjunto muito maior de exemplos. Observe, no entanto, que os desenvolvimentos geralmente são feitos na biblioteca sem considerar a compatibilidade com versões anteriores desses vídeos antigos. Para executar um projeto antigo com garantia de que funcionará, você terá que voltar ao commit que completou aquele projeto.

### Documentação
A documentação está em andamento em [3b1b.github.io/manim](https://3b1b.github.io/manim/). E também há uma versão chinesa mantida por [**@manim-kindergarten**](https://manim.org.cn): [docs.manim.org.cn](https://docs.manim.org .cn/) (em chinês).

[manim-kindergarten](https://github.com/manim-kindergarten/) escreveu e coletou algumas aulas extras úteis e alguns códigos de vídeos em [manim_sandbox repo](https://github.com/manim-kindergarten/manim_sandbox ).


## Contribuindo
É sempre bem-vindo. Como mencionado acima, a [edição da comunidade](https://github.com/ManimCommunity/manim) tem o ecossistema mais ativo para contribuições, com testes e integração contínua, mas pull requests são bem-vindos aqui também. Por favor, explique a motivação para uma determinada mudança e exemplos de seu efeito.



## Licença
Este projeto se enquadra na licença MIT.
