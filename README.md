# MyRadar Desktop — Weddbets (5.5.64)

## Correção crítica de vídeo

A Weddbets é aberta pelo próprio MyRadar em uma janela isolada do **Google Chrome**, sem barra de navegação e com um perfil exclusivo do aplicativo. Esse modo utiliza os codecs e o DRM do Chrome instalado no Windows, que são necessários para provedores de vídeo que não funcionam no Chromium interno do Electron.

- A extensão MyRadar é carregada internamente apenas nessa janela: o usuário não precisa instalar ou configurar extensão no Chrome pessoal.
- O login da Weddbets fica salvo no perfil exclusivo do MyRadar. Depois de entrar uma vez, as próximas aberturas reutilizam os cookies.
- A licença continua centralizada no MyRadar e é validada no máximo uma vez por dia. Nenhum popup de licença aparece na transmissão.
- Ao fechar uma transmissão, o MyRadar reabre a listagem de jogos da Weddbets. Fechando essa listagem, o MyRadar é encerrado.
- É necessário ter o **Google Chrome atualizado** instalado no Windows.

## Gerar instalador

```powershell
npm install
npm run dist:win
```

Arquivos:

```text
release\MyRadar-Setup-5.5.64.exe
release\MyRadar-Portable-5.5.64.exe
```


## Correção 5.5.65

- Ao abrir uma transmissão da Weddbets pelo Chrome isolado, o MyRadar normaliza a URL para `?view=clean` antes de inicializar os componentes.
- Isso evita que a página seja aberta sem a interface da extensão quando a Weddbets fornece uma rota `/view/...` sem o parâmetro necessário.
