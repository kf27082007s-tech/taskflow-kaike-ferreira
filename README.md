# TaskFlow · Gestão de manutenção

Aplicação demonstrativa para abertura e acompanhamento de chamados de manutenção em um quadro Kanban. Feita com HTML, CSS e JavaScript, sem etapa de build.

## Executar

Abra `index.html` em um navegador moderno. Também é possível servir a pasta com qualquer servidor estático. Crie uma conta para acessar o painel.

## Instalar como app

O TaskFlow também pode ser instalado como PWA no computador ou celular. No VS Code, abra a pasta `TaskFlow_Atividade`, clique com o botão direito em `index.html` e escolha **Open with Live Server** (a extensão Live Server precisa estar instalada). No navegador, use **Instalar app** ou o menu **Instalar aplicativo / Adicionar à tela inicial**. A instalação exige `localhost` ou HTTPS; abrir o arquivo diretamente (`file://`) não habilita o modo instalável. Depois da primeira visita online, os arquivos do app ficam disponíveis offline.

Os dados do `localStorage` são separados por endereço. Se você já criou uma conta usando `file://`, crie outra quando abrir pela primeira vez em `localhost`.

## APK Android

O projeto Android está na pasta `android/` e usa Capacitor. Com Android SDK API 36, Android Build Tools 36 e JDK 21 instalados, execute `npm run android:apk` nesta pasta. O script atualiza os arquivos do site e copia o APK de depuração para `TaskFlow-debug.apk`. Esse APK pode ser instalado manualmente em um aparelho; para publicar na Play Store, gere e assine uma versão de lançamento.

O ícone do atalho Android é gerado a partir de `icons/taskflow-android-icon-source.png` por `scripts/generate-android-icon.ps1`.

## Perfis

- **Funcionário:** abre chamados, acompanha os próprios e pode cancelar os próprios chamados ainda ativos.
- **Técnico / Mecânico e Coordenador:** acompanham todos os chamados, alteram status e excluem chamados não concluídos.

O cadastro permite selecionar o perfil para facilitar a demonstração.

## Chamados e regras

- Código sequencial no formato `CP-0001`.
- Todos os campos são obrigatórios; a urgência pode ser baixa, média ou alta.
- Status inicial **Em andamento**; demais status: **Pausado**, **Concluído** e **Cancelado**.
- Chamados concluídos não podem ser alterados ou excluídos. Chamados cancelados não podem ser reabertos.
- Busca textual e filtros por status, urgência e localização.
- Notificações internas para criação e atualizações; ação para limpar as notificações.

## Persistência e limites

Contas, sessão, chamados e notificações ficam no `localStorage` do navegador. A redefinição de senha é apenas local e não envia e-mail. Este projeto é uma demonstração de atividade: não use informações reais ou sensíveis. Senhas não são armazenadas com proteção adequada, os perfis são escolhidos no cadastro e os dados não são sincronizados entre dispositivos.
