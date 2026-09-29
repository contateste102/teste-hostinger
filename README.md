# Fio Studio

Landing page estática em HTML, CSS e JavaScript, sem build nem dependências. Textos, imagens e identidade visual são uma demonstração e devem ser adaptados à sua marca.

## Executar localmente

Abra `index.html` no navegador ou use a extensão Live Server do VS Code.

## Publicar automaticamente na Hostinger

O workflow em `.github/workflows/deploy.yml` envia os arquivos por FTPS a cada `push` para a branch `main`. Também é possível iniciar uma publicação manual na aba **Actions** do GitHub.

1. Envie este projeto para um repositório no GitHub e mantenha a branch de publicação chamada `main`.
2. No hPanel da Hostinger, abra o gerenciamento do site e consulte ou crie os dados de acesso FTP. Confirme o host FTP e o caminho da pasta raiz; em muitos planos é `public_html/`, mas use o caminho exibido para o seu domínio.
3. No GitHub, abra **Settings > Secrets and variables > Actions > New repository secret** e cadastre:

   | Nome | Valor |
   | --- | --- |
   | `FTP_SERVER` | Host FTP da Hostinger, sem `ftp://` |
   | `FTP_USERNAME` | Usuário FTP |
   | `FTP_PASSWORD` | Senha FTP |
   | `FTP_SERVER_DIR` | Pasta raiz do domínio, terminando em `/` |

4. Faça um `push` para `main`. Acompanhe o resultado em **Actions** e abra o domínio para conferir a publicação.

O workflow usa FTPS explícito na porta 21 e não executa limpeza total da pasta remota. O primeiro deploy pode substituir arquivos com o mesmo nome, como `index.html`; confirme que a pasta escolhida pertence ao site correto. Nunca coloque senhas no código ou neste repositório.

Antes de publicar, personalize a marca, os textos, as imagens e o e-mail de contato em `index.html`.