# Changelog

Todas as mudancas notaveis do APEX sao documentadas neste arquivo.

O formato segue [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/)
e este projeto adere ao [Versionamento Semantico](https://semver.org/lang/pt-BR/).

## [Nao lancado]

## [0.17.0] - 2026-10-26

### Adicionado
- Sistema de atualizacoes integrado (GitHub Releases).
- Verificacao automatica ao iniciar, com aviso quando houver nova versao.
- Dialogo de atualizacao com changelog, tamanho do download e barra de progresso.
- Download com verificacao SHA256 (integridade garantida) e instalacao automatica:
  o Apex se reinicia com a nova versao sem intervencao do usuario.
- Modo silencioso: baixa e instala automaticamente sem perguntar.
- Nova secao em Configuracoes > Geral > ATUALIZACOES, com botao "VERIFICAR AGORA".
- Versionamento semantico: cada release tem tag `vX.Y.Z`.

### Alterado
- Release "latest" agora aponta sempre para a versao mais recente.

### Corrigido
- Comparacao de versoes (`IsNewer`) nao gera mais falso positivo
  quando a versao remota tem revision zerada (`0.17.0` vs `0.17.0.0`).
- Consulta a `/releases` (lista) em vez de `/releases/latest`, que retornava 404
  em repositorios com releases ainda em rascunho.

## [0.16.0] - 2026-10-20

### Adicionado
- Nova pagina APEX FERRAMENTAS > Inicializacao: lista programas que abrem com o Windows
  (chaves Run do registro e pastas Inicializar), com descricao, fabricante e aviso
  quando o arquivo do programa nao existe mais.
- Interruptor para ativar/desativar entradas de inicializacao (mesmo modelo do
  Gerenciador de Tarefas: a entrada continua la e pode ser religada).
- Botao REMOVER com confirmacao; o programa continua instalado e tudo pode ser
  desfeito em "Restaurar removidos".
- Nova pagina APEX FERRAMENTAS > Instalar apps: essenciais pos-formatacao via winget
  (Steam, Google Chrome, Discord, Lightshot, 7-Zip, WinRAR e VLC).
- APEX MAKER: suporte a portas COM e drivers seriais CH340/CP210x/FTDI/Prolific/Arduino.
- Abertura rapida: janela aparece imediatamente, hardware carregado em paralelo.

## [0.12.0] - 2026-09-15

### Adicionado
- Sistema de tags: cada tag `vX.Y.Z` gera uma release fixa no GitHub.

[0.17.0]: https://github.com/notvictornw/apex/compare/v0.16.0...v0.17.0
[0.16.0]: https://github.com/notvictornw/apex/compare/v0.12.0...v0.16.0
[0.12.0]: https://github.com/notvictornw/apex/releases/tag/v0.12.0
