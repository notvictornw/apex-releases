# Changelog

Todas as mudancas notaveis do APEX sao documentadas neste arquivo.

O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/)
e este projeto adere ao [Versionamento Semantico](https://semver.org/lang/pt-BR/).

## [Nao lancado]

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

[0.17.9]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.9
[0.17.8]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.8
[0.17.7]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.7
[0.17.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.17.0
[0.16.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.16.0
[0.12.0]: https://github.com/notvictornw/apex-releases/releases/tag/v0.12.0

