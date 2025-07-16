# YLauncher

![Preview do Launchpad (placeholder)](https://i.postimg.cc/BZKykxtk/image.png)

## Descrição

O **YLauncher** é um lançador de aplicativos minimalista e altamente personalizável, desenvolvido em Python com a biblioteca GTK3, projetado especificamente para usuários Linux. Ele foi criado para oferecer uma maneira rápida e eficiente de acessar e organizar seus aplicativos, com foco em atalhos `.desktop` personalizados.

O design foi inspirado no layout do LaunchPad do MacOS.

## Recursos

* **Interface GTK3:** Leve e integrada à maioria dos ambientes de desktop Linux.
* **Lançamento Rápido:** Inicie seus aplicativos favoritos com um clique ou através da busca.
* **Pesquisa Instantânea:** Filtre seus aplicativos rapidamente digitando na barra de pesquisa.
* **Paginação Inteligente:** Navegação fluida entre páginas de aplicativos, otimizada para diferentes tamanhos de tela e configurações de layout.
* **Layout Personalizável:** Configure o número de colunas, linhas por página e tipo de transição entre as páginas (slide, crossfade, etc.).
* **Fundo Customizável:** Defina uma imagem de fundo para o lançador ou use uma cor sólida.
* **Gerenciamento de Lançadores:** Clique com o botão direito nos ícones dos aplicativos para:
    * **Editar:** Altere o nome, comando, ícone e outras propriedades de um lançador.
    * **Excluir:** Remova facilmente atalhos de aplicativos que não são mais necessários.
* **Fechamento Automático:** O Launchpad fecha automaticamente quando perde o foco (comportamento de um pop-up launcher), mas permanece aberto para edições e exclusões com o botão direito.
* **Navegação por Teclado:** Use as setas para navegar entre as páginas e `Esc` para limpar a pesquisa ou fechar o lançador.
* **Pasta de Lançadores Customizados:** Gerencia arquivos `.desktop` em um diretório dedicado para seus atalhos pessoais (`~/.local/share/applications/launchpad/`).

## Pré-requisitos

Para rodar o YLauncher, você precisará:

* Python 3.x
* PyGObject (para bindings GTK3)

## Instalação

1.  **Clone o repositório:**
    ```bash
    git clone [htthttps://github.com/kvsdc/YLauncher.git](https://github.com/kvsdc/YLauncher.git)
    cd YLauncher
    ```
    
2.  **Instale as dependências:**
    ```bash
    pip install PyGObject
    # Ou, para sistemas baseados em Debian/Ubuntu:
    # sudo apt install python3-gi python3-gi-cairo gir1.2-gtk-3.0
    ```

3.  **Crie a pasta para seus lançadores personalizados:**
    O Launchpad busca e gerencia seus atalhos personalizados nesta pasta.
    ```bash
    mkdir -p ~/.local/share/applications/launchpad/
    ```
    Você pode colocar seus arquivos `.desktop` personalizados aqui. Ex: `meu_app.desktop`.

4.  **Crie a pasta de configuração:**
    ```bash
    mkdir -p ~/.config/launchpad/
    ```

## Uso

1.  **Execute o Launchpad:**
    ```bash
    python3 main.py
    ```

2.  **Atribua um Atalho de Teclado (Opcional, mas Recomendado):**
    Para uma experiência completa, é altamente recomendado atribuir uma tecla de atalho (por exemplo, a tecla <kbd>Super</kbd> ou <kbd>Windows</kbd>) para executar o comando `python3 /caminho/para/ylauncher/main.py`. As etapas variam dependendo do seu ambiente de desktop (GNOME, KDE, XFCE, etc.). Geralmente, você pode fazer isso nas configurações de "Atalhos de Teclado" ou "Teclas Personalizadas".

3.  **Adicionar/Editar/Excluir Lançadores:**
    Coloque seus arquivos `.desktop` personalizados na pasta `~/.local/share/applications/launchpad/`.
    Com o Launchpad aberto, clique com o **botão direito** em qualquer ícone para exibir as opções de "Editar Lançador" e "Excluir Lançador".

## Configuração

O Launchpad carrega suas configurações do arquivo `~/.config/launchpad/config.ini`. Se este arquivo não existir, ele usará as configurações padrão. Você pode editá-lo manualmente ou usar o botão de **"Configurações"** (ícone de engrenagem) dentro do próprio aplicativo.

Exemplo de `config.ini`:

```ini
[Launcher]
num_cols = 5
max_rows_per_page = 3
transition_type = slide-left-right
transition_duration = 200
background_image_path = /home/seu_usuario/Imagens/minha_imagem_de_fundo.png
