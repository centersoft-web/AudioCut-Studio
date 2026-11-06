# AudioCut Studio

Editor de áudio multipista executado diretamente no navegador, com processamento em tempo real, gerenciamento de projetos e exportação em WAV ou MP3.

O AudioCut Studio foi desenvolvido como uma aplicação HTML única, sem instalação. A edição e o processamento principal dos arquivos acontecem localmente no navegador.

## Principais recursos

### Edição de áudio

- Importação de múltiplos arquivos de áudio
- Arrastar e soltar arquivos na área de edição
- Visualização da forma de onda
- Corte do início e do fim de cada faixa
- Divisão de uma faixa na posição do cursor
- Duplicação e exclusão de faixas
- Inserção de trechos de silêncio
- Reordenação de faixas
- Reprodução contínua durante os ajustes

### Mixagem

- Modo **Sequência**, para reproduzir as faixas uma após a outra
- Modo **Mixagem multipista**, para reproduzir faixas simultaneamente
- Definição do momento de entrada de cada faixa
- Ganho individual
- Pan estéreo
- Mudo
- Solo
- Volume master

### Equalização e dinâmica

- Equalizador gráfico de 10 bandas
- Presets Flat, Voz/Podcast, Bass Boost, Brilho, Rock e Suave
- Compressor
- Controle de limiar e proporção
- Limitador de segurança
- Normalização da faixa selecionada

### Efeitos

- Fade in
- Fade out
- Reverberação
- Tamanho da sala
- Delay com alteração protegida por microfade
- Feedback do Delay
- Saturação
- Aplicação dos controles em tempo real

### Projetos

- Criação de um projeto novo
- Salvamento por meio de **Salvar projeto como…**
- Lista de projetos armazenados no navegador
- Abertura de projetos salvos
- Renomeação
- Duplicação
- Exclusão

Os projetos são armazenados no IndexedDB do navegador. Para reencontrá-los, abra o mesmo `index.html` no mesmo navegador e clique em **Projetos**.

> Atenção: limpar os dados do navegador, mudar de navegador, usar uma janela privativa ou abrir outra cópia do arquivo em um contexto diferente pode impedir o acesso aos projetos armazenados anteriormente.

## Exportação

Formatos disponíveis:

- WAV 16-bit
- WAV 24-bit
- MP3 128 kbps
- MP3 192 kbps
- MP3 320 kbps

A exportação aplica os cortes, a mixagem, os fades, o ganho, o pan, a equalização, o compressor, o limitador, a reverberação, o Delay, a saturação e o volume master.

A codificação MP3 é executada em uma tarefa separada para ajudar a manter a interface responsiva. É possível cancelar a exportação pelo botão **Cancelar exportação**.

## Requisitos

- Navegador moderno com suporte à Web Audio API
- JavaScript habilitado
- Conexão com a internet para carregar o codificador LAME.js usado na exportação MP3
- Espaço disponível no armazenamento do navegador para guardar projetos

Para melhor compatibilidade, use uma versão atual do Microsoft Edge ou Google Chrome.

## Como usar

1. Baixe o arquivo `index.html`.
2. Abra o arquivo em um navegador compatível.
3. Use o seletor de arquivos ou arraste os áudios para a área central.
4. Escolha entre **Sequência** e **Mixagem multipista**.
5. Faça os cortes e ajustes necessários.
6. Configure equalização, dinâmica, efeitos e volume master.
7. Digite o nome do projeto.
8. Clique em **Salvar projeto como…** para guardar uma cópia no navegador.
9. Escolha o formato desejado na seção **Exportação**.
10. Clique em **Exportar áudio**.

## Recuperação de projetos

1. Abra o mesmo `index.html` no mesmo navegador usado para salvar.
2. Clique em **Projetos**.
3. Localize o projeto pelo nome, data e hora.
4. Clique em **Abrir**.

Na mesma janela, também é possível renomear, duplicar ou excluir um projeto.

## Estrutura do projeto

```text
AudioCut Studio/
├── index.html
└── README.md
```

O arquivo `index.html` reúne a interface, os estilos e a lógica principal da aplicação.

## Privacidade

Os arquivos de áudio são processados localmente no navegador. O AudioCut Studio não possui, por padrão, um servidor próprio para receber as músicas importadas.

A biblioteca externa usada na exportação MP3 é carregada pela internet. A exportação WAV não depende do codificador MP3.

## Limitações conhecidas

- Projetos muito longos ou com muitas faixas podem exigir bastante memória.
- A renderização inicial da exportação pode consumir processamento mesmo com a codificação MP3 em segundo plano.
- O navegador pode mostrar temporariamente a extensão `.crdownload` enquanto conclui um download.
- O armazenamento de projetos depende dos dados locais do navegador.
- A exportação MP3 depende do carregamento do LAME.js.

## Segurança dos arquivos

Mantenha cópias dos áudios originais. A edição é não destrutiva, mas os projetos salvos no navegador não devem ser considerados um substituto para um backup externo.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript
- Web Audio API
- OfflineAudioContext
- Canvas API
- IndexedDB
- Web Workers
- LAME.js para codificação MP3

  ### Instalação no computador

### No Google Chrome ou Microsoft Edge:

  1. Abra o endereço publicado do projeto.
  2. Aguarde o carregamento completo da página.
  3. Clique no ícone de instalação exibido na barra de endereço ou abra o menu do navegador.
  4. Selecione Instalar aplicativo ou Instalar este site como aplicativo.
  5. Confirme a instalação.

Depois disso, o aplicativo poderá ser aberto pelo menu Iniciar, pela área de trabalho ou pelo gerenciador de aplicativos do sistema.

### Instalação no celular ou tablet

### Em navegadores compatíveis:

1. Abra o endereço do projeto.
2. Acesse o menu do navegador.
3. Selecione Instalar aplicativo ou Adicionar à tela inicial.
4. Confirme o nome e a instalação.

O ícone será adicionado à tela inicial do dispositivo.

**Observações**

A disponibilidade e o nome da opção de instalação podem variar conforme o navegador e o sistema operacional.
Abrir somente o arquivo index.html pelo computador não garante a instalação como PWA.
O projeto deve ser publicado em HTTPS para utilizar os recursos completos de instalação e service worker.
O funcionamento offline depende da configuração do service-worker.js e dos arquivos adicionados ao cache.
Atualizações no projeto podem exigir a atualização da versão do cache do service worker.

## Licença

Nenhuma licença específica foi definida no arquivo fornecido. Antes de distribuir ou publicar o projeto, inclua uma licença compatível com a finalidade pretendida e verifique as licenças das bibliotecas externas utilizadas.


## Aviso

> Este projeto é uma demonstração educacional desenvolvida para estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia e qualquer semelhança com empresas reais é mera coincidência.


## Créditos

Projeto desenvolvido de forma colaborativa como uma ferramenta de edição e mixagem de áudio executada no navegador.
