# Apex

Ferramenta de otimização e manutenção para Windows.

- **Código-fonte:** privado (`notvictornw/apex`)
- **Site / Download:** <https://notvictornw.github.io/apex-releases/>
- **Changelog:** [CHANGELOG.md](CHANGELOG.md)

## Download

[![Latest release](https://img.shields.io/github/v/release/notvictornw/apex-releases)](https://github.com/notvictornw/apex-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/notvictornw/apex-releases/total)](https://github.com/notvictornw/apex-releases/releases)

| Pacote | Link |
|---|---|
| **Instalador** (recomendado) | [Releases → latest](https://github.com/notvictornw/apex-releases/releases/latest) |
| **Portable** (.zip, sem instalação) | [Download direto](https://github.com/notvictornw/apex-releases/releases/latest/download/Apex.zip) |

> O instalador tem a versão no nome do arquivo (ex.: `Apex-Setup-0.17.9.exe`), então o link aponta para a página da release latest. O portable se chama sempre `Apex.zip`, então o link direto sempre baixa a última versão.

## Atualizações

O Apex verifica atualizações automaticamente ao iniciar (Configurações → Geral → Atualizações) usando o [manifest.json](manifest.json) publicado neste repositório via GitHub Pages. Não é preciso voltar aqui para baixar novas versões.

### Integridade

O SHA256 de cada binário está publicado no [manifest.json](manifest.json). Para conferir manualmente:

```powershell
Get-FileHash .\Apex-Setup-0.17.9.exe -Algorithm SHA256
```
