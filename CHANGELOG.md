# Changelog

Todas as mudancas notaveis do APEX sao documentadas neste arquivo.

O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/)
e este projeto adere ao [Versionamento Semantico](https://semver.org/lang/pt-BR/).

## [Nao lancado]

## [0.36.1] - 2026-11-18

### Adicionado
- menu lateral unico com grupos recolhiveis (categorias e subcategorias) - remove as barras de abas dos hubs

## [0.36.0] - 2026-11-06

### Alterado
- Navegacao de volta ao menu lateral unico: grupos recolhiveis com categorias
  e subcategorias visiveis (Otimizacao, Jogos, Desempenho, Hardware,
  Sistema), como no menu original. Removidas as barras de abas superiores
  das paginas - tudo se alcanca pelo menu lateral.
- Reduzidos elementos de navegacao redundantes dentro das paginas.
## [0.35.1] - 2026-11-18

### Adicionado
- Energia vira sub-aba do Otimizar e Configuracoes enxuta (Overlay/Bench/Portas COM realocadas) - menu final com 10 itens
- menu em hubs (23 -> 10 itens) com sub-abas nas paginas e NavigateTo sem depender do RadioButton

## [0.35.0] - 2026-11-06

### Adicionado
- Menu redesenhado: de 23 itens para 10 entradas claras, cada uma com
  sub-abas na propria pagina (Desempenho, Jogos, Hardware, Drivers,
  Manutencao). Nada foi removido - tudo ficou mais facil de achar.
- Energia agora e uma sub-aba do Otimizar.
- Configuracoes enxuta: as opcoes de Overlay foram para a pagina Overlay
  (Jogos), as opcoes avancadas do teste para o Desempenho e as Portas COM
  para Drivers seriais.
- Feedback visual consistente: indicador girando em operacoes, pontos de
  estado coloridos, banners de sucesso/aviso/erro e barra de progresso em
  lote com cancelamento.

## [0.34.1] - 2026-11-17

### Adicionado
- sistema de feedback visual (spinner, dots, banners, BatchBar) e navegacao unificada (NavigateTo + PageRegistry)
- barra de GRUPOS com aplicacao em lote e criacao de grupo por selecao multipla; remove pacote ProtectedData redundante
- assistente de IA integrado (API compativel OpenAI) com recomendacoes de otimizacao aplicaveis com revisao
- ducking por fases do Valorant (log do jogo), escolha livre de apps e status amigavel
- atalho do Auto Mute Music no painel do jogo com botao Configurar
- Auto Mute Music no modelo real do Overwolf - ducking por volume com fade, mute opcional e ducking do volume mestre
- bandeja do sistema com atalhos, Auto Mute Music (silencio de apps ao jogar) e nome do app 'Apex Performance'
- aplica o perfil AMD curado no fluxo de otimizacao e ativa afinidade de CPU por jogo
- liga otimizacao AMD por-jogo, revert global real, modo de jogo automatico, trava anti-crash e corrige tweaks de energia no-op
- icone de ajuda corrigido, filtro de jogos, config do jogo redesenhada, plano de energia selecionavel, recs do Windows acionaveis e textos enxutos
- licenca em pt-BR quando o idioma for portugues
- painel do jogo em abas (Otimizar/Graficos/Config do jogo/Programas)
- recomendacoes em lista enxuta, agrupadas por categoria e expandiveis
- aba Driver AMD, editor de config do jogo com presets e reverter, guias ampliados (Valorant/CS2/LoL)
- integracao ADL2/UMD por jogo e global, UI AMD, validacao ao vivo
- capacidades por jogo, perfis de energia, biblioteca/rede e Adrenalin
- migração WPF + Fases A-D (bugs, performance, segurança, features)

### Alterado
- elimina travamentos da UI - deteccao de jogo, modo de jogo, WMI, powercfg e salvamento fora da thread da UI
- painel de otimizacao em acoes + instrucoes, sem vazamento de argumentos entre jogos

### Corrigido
- corrige bugs de otimizacao, textos e adiciona tooltips explicativos (?)
- corrige ortografia pt-BR em textos do app, i18n, licenca e instalador
- corrige titular do copyright (Apex Performance / NotVictorNW)

## [0.34.0] - 2026-11-06

### Adicionado
- Barra de GRUPOS na pagina Otimizar: aplique varios ajustes de uma vez
  clicando em um grupo (Gamer, Ultra, Streamer, Bateria e os seus), com
  ponto de restauracao, progresso e resumo do resultado.
- Modo SELECIONAR: marque varios ajustes na lista e aplique todos de uma
  vez, ou salve a selecao como um grupo novo para reutilizar depois.

## [0.33.0] - 2026-11-06

### Adicionado
- Assistente de IA integrado: configure qualquer servico compativel com a API
  da OpenAI (OpenAI, OpenRouter, Groq, Ollama local...) em Configuracoes > IA
  (endereco, chave e modelo). A chave fica criptografada neste PC.
- Otimizar > Assistente IA: descreva seu objetivo (ex.: "mais FPS no
  Valorant") e a IA analisa seu hardware e o estado atual dos ajustes,
  sugerindo ate 10 recomendacoes com motivo. Voce revisa e aplica cada uma
  com um clique - nada e aplicado sozinho, e tudo pode ser revertido.

## [0.32.0] - 2026-11-06

### Adicionado
- Auto Mute Music por FASES DO JOGO (começando pelo VALORANT): o app le o
  estado da partida direto do log do jogo (leitura passiva, sem risco) e
  abaixa/silencia a musica durante a partida e, se voce quiser, na selecao
  de agente - devolvendo o som no menu e no fim da partida.
- Painel de status simples: VALORANT rodando ou fechado, fase atual e o que
  esta acontecendo com a musica agora.
- Controle total dos apps: escolha quais apps tem o volume abaixado, remova
  qualquer sugestao e adicione apps proprios pelo nome.

### Alterado
- A lista de apps agora e a sua escolha: as sugestoes vem marcadas na
  primeira vez, e a partir dai voce decide tudo.

## [0.31.0] - 2026-11-06

### Corrigido
- Desempenho: eliminados os principais travamentos da interface.
  - A deteccao de jogos em execucao (que rodava a cada 3 segundos na thread
    da interface e podia travar segundos com um jogo aberto) agora roda em
    segundo plano.
  - Ligar/desligar o Modo de Jogo nao trava mais a tela (os comandos de
    energia e a suspensao de apps agora rodam em segundo plano).
  - A pagina Jogos nao faz mais duas consultas WMI a cada visita (o nome do
    processador e resolvido uma unica vez, em segundo plano).
  - Selecionar um jogo nao executa mais powercfg nem re-ler o arquivo de
    configuracao da Steam a cada clique (listas e leituras agora usam cache
    e segundo plano).
  - Arrastar sliders e digitar nao salva mais o arquivo de configuracao a
    cada tick (salvamento agrupado, gravado em segundo plano e sempre
    concluido ao sair).

## [0.30.1] - 2026-11-06

### Adicionado
- Atalho do Auto Mute Music no painel do jogo (cartao "O APEX FAZ POR VOCE"):
  liga/desliga na hora e um botao CONFIGURAR abre a tela completa em
  Configuracoes > Geral. As tres entradas (painel, bandeja e configuracoes)
  ficam sempre em sincronia.

## [0.30.0] - 2026-11-06

### Alterado
- Auto Mute Music atualizado para o modelo real do app original: em vez de
  apenas silenciar, agora ABAIXA o volume dos apps escolhidos com uma
  transicao suave (fade) e devolve o volume original ao sair do jogo.
  Novas opcoes: modo (abaixar volume / silenciar), volume durante o jogo,
  duracao da transicao e opcao de abaixar tambem o volume geral do sistema.

## [0.29.0] - 2026-11-06

### Adicionado
- Icone na bandeja (system tray) com atalhos rapidos: abrir, ligar/desligar
  Modo de Jogo, ligar/desligar Overlay, ligar/desligar Auto Mute Music, abrir
  pasta de configuracao/logs e "Fechar o Apex Performance" (encerra de vez).
  Fechar a janela agora minimiza para a bandeja (configuravel).
- Auto Mute Music: silencia automaticamente os apps de musica/navegador
  quando voce esta em um jogo e devolve o som ao sair. Voce escolhe quais
  apps (lista de quem esta tocando audio). Sem pedir administrador.
- Nome do aplicativo no Windows alterado para "Apex Performance".

## [0.28.0] - 2026-11-06

### Adicionado
- Otimizacao por jogo agora aplica tambem o perfil de driver AMD curado
  (Anti-Lag, Chill, Boost, sharpening, etc.) junto dos ajustes do Windows,
  em um unico botao - antes o perfil AMD curado nao era aplicado.
- Afinidade de CPU por jogo (usar todos os nucleos ou apenas os fisicos),
  para usuarios avancados.

### Corrigido
- AMD por jogo voltou a funcionar: o motor existia mas nao estava ligado ao
  aplicativo (o botao respondia "nao suportado").
- Reverter os ajustes globais da AMD agora realmente desfaz (antes dizia
  reverter mas deixava Anti-Lag/Chill/Boost aplicados).
- Perfil AMD nao e mais perdido se uma gravacao falhar no meio (restaura o
  estado anterior automaticamente).
- Modo de Jogo agora liga sozinho quando um jogo e detectado e desliga ao
  sair (antes so funcionava no botao manual). O passo "suspender apps" nao e
  mais contado como ajuste quando nao suspende nada.
- Se o APEX for fechado no meio de um jogo, o plano de energia temporario e
  restaurado na proxima abertura (antes ficava preso).
- Ajustes de energia que nao faziam nada agora aplicam de verdade via
  powercfg no plano ativo: Modo de Impulso, Estacionamento de Nucleos e
  Estado Minimo do Processador.
- Ajustes especificos de fabricante (AMD/NVIDIA/Intel) so aparecem na marca
  certa; adicionada a chave de Prioridade de GPU no MMCSS; corrigidos os
  atalhos de acessibilidade.

## [0.27.0] - 2026-11-06

### Adicionado
- Plano de energia da biblioteca de jogos agora e um seletor: escolha qualquer
  plano do Windows (ou "seguir o padrao do APEX" / "nao alterar").
- Recomendacoes que sao ajustes do Windows (timer resolution, Game Bar/DVR,
  plano de energia, HAGS, otimizacao de tela cheia) aparecem em uma secao
  "Aplicar no Windows" com botao APLICAR/REVERTER - o APEX aplica por voce.

### Alterado
- Editor de configuracao do jogo redesenhado: cada opcao agora tem nome
  amigavel (ex.: "sg.ShadowQuality" -> "Qualidade das sombras"), uma
  explicacao curta, e o controle certo (interruptor, lista ou numero),
  agrupado por secao. A secao inutil "linhas nao editaveis" foi removida.
- Textos das recomendacoes por jogo encurtados (menos texto, mais acao).
- Icone de ajuda "?" corrigido (antes aparecia como quadrado) e a explicacao
  agora aparece em ~0,2s.

### Corrigido
- Biblioteca de jogos nao lista mais servicos, runtimes, SDKs,
  redistribuiveis e anti-cheats como se fossem jogos.

## [0.26.0] - 2026-11-05

### Adicionado
- Explicacoes de ajuda (icone "?"): passe o mouse e aparece uma explicacao
  simples do que o ajuste faz. Cobre otimizacao, overclock, rede, drivers,
  energia, stress test, limpeza/seguranca, overlay e alertas.

### Corrigido
- Limpeza de cache de navegador e do Windows voltou a funcionar: o guard de
  seguranca bloqueava, por engano, todas as pastas de cache sob o perfil do
  usuario, e nada era removido. Agora usa uma lista restrita de cache seguro.
- Reparo de notificacoes/GameDVR: comandos de registro passaram a gravar os
  valores como DWORD (antes eram gravados como texto e o Windows ignorava).
- Plano de energia: reverter nao perde mais o plano original do usuario.
- Aplicar/reverter ajustes agora usa o resultado real da operacao (nao mostra
  mais "FALHOU" quando o ajuste foi aplicado corretamente).
- Overclock/FileShredder e caminhos de limpeza deixaram de depender de "C:\"
  fixo e de arquivos somente-leitura.
- Varios textos fora de contexto corrigidos e rotulos com acentuacao ajustada.

## [0.25.1] - 2026-11-05

### Corrigido
- Ortografia do portugues corrigida em todo o aplicativo (acentos, cedilha e
  grafia): textos da interface, mensagens, catalogos de ajustes, recomendacoes
  por jogo e documentacao.
- Licenca exibida na instalacao: titular corrigido para Apex Performance /
  NotVictorNW. Agora a licenca aparece em portugues quando o idioma escolhido
  no instalador e o portugues (e em ingles quando for ingles).

## [0.25.0] - 2026-11-05

### Alterado
- Redesign do painel de otimizacao por jogo. A aba agora separa claramente
  o que o APEX aplica por voce (linhas com interruptor: plano de energia,
  GPU dedicada, tela cheia/FSO, prioridade) das recomendacoes que sao
  instrucoes para fazer dentro do jogo. As instrucoes ficam em listas
  recolhidas ("No jogo" e "Fora do jogo"), em uma linha cada, com detalhe
  sob demanda — acabou o paredao de texto.
- Aba "Graficos" renomeada para "Tela & Lancamento" e reorganizada. O
  bloco de argumentos de lancamento (e a "linha final") passa a aparecer
  SOMENTE para jogos que de fato aceitam argumentos; títulos como Valorant
  mostram apenas uma nota curta explicando o motivo, sem vocabulario de
  outra engine.
- Removido o botao "Perfil para mais FPS", que forcava prioridade Alta —
  contrariando a recomendacao curada do proprio titulo.

### Corrigido
- Estado dos argumentos de lancamento nao vaza mais ao trocar de jogo
  (o campo do jogo anterior podia ser gravado no perfil do novo).
- Rotulos genericos de engine ("Source / CS2") deixaram de aparecer em
  jogos que nao sao Source.

## [0.24.1] - 2026-11-05

### Alterado
- Painel do jogo (aba APEX JOGOS) reorganizado em abas: OTIMIZAR
  (recomendacoes + desempenho), GRAFICOS, CONFIG DO JOGO e PROGRAMAS. O
  editor de arquivos de configuracao do jogo agora tem aba propria e fica
  visivel de imediato, em vez de no fim de uma rolagem longa.
- Recomendacoes por jogo exibidas em lista enxuta, agrupadas por categoria
  e com detalhes/porque recolhidos sob demanda (menos texto de uma vez).

## [0.24.0] - 2026-11-05

### Adicionado
- Aba propria "Driver AMD" na barra lateral, dentro do grupo HARDWARE,
  logo apos "Placa de video". Os cartoes de configuracao do driver
  (global + por jogo) sairam da aba "Integracao", onde ficavam pouco
  visiveis, e agora tem um lugar dedicado.
- Editor de arquivos de configuracao do jogo na aba APEX JOGOS: le as
  chaves editaveis do arquivo de config (INI, key-value, colon), permite
  alterar valores, abrir no Bloco de Notas / na pasta, e reverter cada
  alteracao (com backup do conteudo anterior).
- Presets prontos por jogo (ex.: Valorant competitivo / qualidade /
  restaurar, CS2, Minecraft), aplicados com confirmacao e reversiveis.
- Guias por jogo ampliados: Valorant (6 -> 31 recomendacoes), CS2
  (6 -> 16) e League of Legends (4 -> 14), cobrindo video, latencia,
  mouse/input, audio, rede e ajustes gerais.

### Alterado
- Deteccao de jogo em execucao trava a edicao da config para evitar
  sobrescrever o arquivo enquanto o jogo o mantem aberto.
- Formatos sem modelo de chave (XML/JSON) sao exibidos somente leitura,
  com opcao de abrir no Bloco de Notas.

## [0.23.0] - 2026-11-04

### Adicionado
- Integracao com o driver da AMD (Adrenalin) via ADL2 (`atiadlxx.dll`) por
  interop limpo, atras de uma interface propria (`IAmdDriverBackend`).
- Configuracao GLOBAL de recursos do driver: Anti-Lag, Chill, Boost,
  Image Sharpening, Frame Rate Target Control, Frame Generation e
  Enhanced Sync (deteccao de capacidade), alem dos valores 3D ja
  existentes via registro UMD (tessellation, filtro anisotropico, TFQ,
  VSync, triple buffering).
- Configuracao POR JOGO: perfil do driver por jogo com overlay de
  recursos sobre a configuracao global, snapshot antes da escrita e
  reversao por jogo.
- Deteccao de divergencia (drift) entre o estado desejado e o que o
  driver expoe, com limpeza apenas de perfis criados pelo APEX.
- Catalogo de recomendacoes enriquecido com overlay AMD por titulo,
  validado por capacidade (so escreve o que o jogo suporta).
- Harness de teste de linha de comando (`amdtest`) para diagnostico e
  validacao reversivel no driver real.

### Alterado
- O antigo `AdlService` experimental foi removido; a logica de ADL foi
  substituida pelos backends auditados (ADL2 + UMD).
- A tela de Adrenalin agora tem os cards GLOBAL e POR JOGO, com estados
  honestos e fail-closed quando o driver/feature nao esta disponivel.

### Corrigido
- Escrita global (ADL2) validada ao vivo: round-trip Anti-Lag Ok no
  driver Radeon RX 6600.
- Criacao de perfil por jogo validada ao vivo com get-modify-set
  (clone + mutacao dos registros do driver), evitando o descarte de
  perfis existentes; driver restaurado ao estado original apos o teste.
- Tratamento defensivo da leitura de perfil existente (sem travamento)
  e tolerancia aos codigos de "nao encontrado" na reversao.

## [0.20.0] - 2026-11-01

### Adicionado
- Adocao do recurso KResetExplode na camada de servicos.
- Passagem de desempenho sobre o carregamento de hardware e o caminho
  de abertura da janela.

### Alterado
- Migracao completa da interface de WinUI 3 para WPF: projeto unico
  Apex.Wpf.csproj, janelas em src\Wpf\*.Wpf.xaml (App.Wpf.xaml,
  MainWindow.Wpf.xaml, SplashWindow.Wpf.xaml, OverlayWindow.Wpf.xaml,
  ToastWindow.Wpf.xaml, CrashDialog.Wpf.xaml, UpdateDialog.Wpf.xaml,
  TelemetryConsentDialog.Wpf.xaml, Theme.Wpf.xaml).
- Repositorios _ported integrados ao build comum.
- Build sem avisos (0 warnings).

## [0.19.0] - 2026-10-30

### Alterado
- Migracao para WPF em andamento: a logica (Services, ViewModels, Utils,
  i18n) passa a ser compartilhada por source linking, sem dependencia de
  WinUI/WindowsAppSDK no build WPF.

### Corrigido
- Exclusoes do glob padrao do SDK para as arvores tests\, cli\ e
  src\_ported\ nos projetos na raiz do repositorio.

## [0.18.0] - 2026-10-29

### Adicionado
- Migracao para WinUI 3: nova interface com o mesmo menu lateral e as
  mesmas categorias RESET do app original.

### Alterado
- Estrutura de projeto reorganizada para a interface WinUI 3.
## [0.17.11] - 2026-11-17

### Corrigido
- notas do manifest passam a usar o primeiro item do changelog

## [0.17.10] - 2026-11-17

### Adicionado
- gera entrada do changelog automaticamente e reescreve links de compare no espelho
- opt-in de telemetria no instalador + leitura do registro

### Corrigido
- acentua palavras portuguesas em strings e comentarios

## [0.17.9] - 2026-10-27

### Adicionado
- Sistema de traducao (i18n) com pt-BR e en-US: infraestrutura Loc, LocManager,
  PluralRules e LocaleMeta, 18 arquivos de locale e migracao de 217 strings
  do MainWindow para recursos dinamicos.
- Dialogo de privacidade (TelemetryConsentDialog) redesenhado com tema
  dinamico e internacionalizacao.
- Opt-in de telemetria no instalador: tela de consentimento no Inno Setup
  (pt-BR/en), gravacao em HKCU\Software\APEX\TelemetryEnabled e ConsentShown
  e leitura pelo aplicativo como fallback quando o JSON nao tem consentimento.

### Corrigido
- Corrupcao de encoding (mojibake UTF-8/CP1252) acumulada em multiplas camadas,
  que afetava acentos, cedilha e simbolos em todo o codigo-fonte
  (56 arquivos corrigidos).
- Mais de 100 palavras PT-BR sem acento em strings literais e comentarios
  (22 arquivos corrigidos).

## [0.17.8] - 2026-10-27

### Adicionado
- Consentimento opt-in de telemetria Sentry (LGPD/GDPR) com toggle em
  Configuracoes.

## [0.17.7] - 2026-10-27

### Adicionado
- Sistema de atualizacao via manifest.json publico hospedado em GitHub Pages
  (notvictornw.github.io/apex-releases/manifest.json), com fallback para o
  CHANGELOG.md quando o manifest nao traz notas.
- Repositorio espelho publico (notvictornw/apex-releases) para distribuicao
  de binarios e manifest, mantendo o codigo-fonte (notvictornw/apex) privado.
- Instalador Inno Setup com versao parametrizada via ISCC /DAppVersion
  (elimina versao hardcoded no .iss).
- CI/CD: build, empacotamento portable, instalador, SHA256, release versionada,
  publicacao no repo espelho e atualizacao do manifest em um unico workflow.
- Crash reporter com dialogo (CrashDialog), coleta de contexto (CPU, GPU, RAM,
  versao do .NET, ultimas 60 linhas do log) e envio opcional para endpoint HTTP.
- Handler de crash pre-startup (AppDomain.UnhandledException).

### Alterado
- Cada push na main gera uma nova versao automaticamente (bump de patch),
  tag vX.Y.Z e release correspondente.
- Release latest agora aponta sempre para a versao mais recente.

### Corrigido
- Comparacao de versoes (IsNewer) nao gera mais falso positivo
  quando a versao remota tem revision zerada (0.17.0 vs 0.17.0.0).
- Consulta a /releases (lista) em vez de /releases/latest, que retornava 404
  em repositorios com releases ainda em rascunho.
- gh release create no repo espelho usa PAT dedicado (MIRROR_PAT) para
  contornar HTTP 403: Resource not accessible by integration.
- Path da deploy key SSH normalizado com Join-Path + escape.
## [0.17.0] - 2026-10-26

### Adicionado
- Sistema de atualizacoes integrado (GitHub Releases).
- Verificacao automatica ao iniciar, com aviso quando houver nova versao.
- Dialogo de atualizacao com changelog, tamanho do download e barra de progresso.
- Download com verificacao SHA256 (integridade garantida) e instalacao automatica:
  o Apex se reinicia com a nova versao sem intervencao do usuario.
- Modo silencioso: baixa e instala automaticamente sem perguntar.
- Nova secao em Configuracoes > Geral > ATUALIZACOES, com botao VERIFICAR AGORA.
- Versionamento semantico: cada release tem tag vX.Y.Z.

### Alterado
- Release latest agora aponta sempre para a versao mais recente.

### Corrigido
- Comparacao de versoes (IsNewer) nao gera mais falso positivo
  quando a versao remota tem revision zerada (0.17.0 vs 0.17.0.0).
- Consulta a /releases (lista) em vez de /releases/latest, que retornava 404
  em repositorios com releases ainda em rascunho.
## [0.16.0] - 2026-10-20

### Adicionado
- Nova pagina APEX FERRAMENTAS > Inicializacao: lista programas que abrem com o Windows
  (chaves Run do registro e pastas Inicializar), com descricao, fabricante e aviso
  quando o arquivo do programa nao existe mais.
- Interruptor para ativar/desativar entradas de inicializacao (mesmo modelo do
  Gerenciador de Tarefas: a entrada continua la e pode ser religada).
- Botao REMOVER com confirmacao; o programa continua instalado e tudo pode ser
  desfeito em Restaurar removidos.
- Nova pagina APEX FERRAMENTAS > Instalar apps: essenciais pos-formatacao via winget
  (Steam, Google Chrome, Discord, Lightshot, 7-Zip, WinRAR e VLC).
- APEX MAKER: suporte a portas COM e drivers seriais CH340/CP210x/FTDI/Prolific/Arduino.
- Abertura rapida: janela aparece imediatamente, hardware carregado em paralelo.

## [0.12.0] - 2026-09-15

### Adicionado
- Sistema de tags: cada tag vX.Y.Z gera uma release fixa no GitHub.

[0.20.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.20.0
[0.19.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.19.0
[0.18.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.18.0
[0.17.9]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.9
[0.17.8]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.8
[0.17.7]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.7
[0.17.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.0
[0.16.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.16.0
[0.12.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.12.0




