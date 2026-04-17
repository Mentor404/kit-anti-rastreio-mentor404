#  Dia 2: O Fim da Telemetria (Hardening de Navegador)

Se você usa o navegador como ele vem de fábrica, a real é que você está trabalhando de graça para empresas de anúncios. Cada clique seu vira telemetria no banco de dados deles.

Hoje, a gente cortou esse mal pela raiz. O objetivo do Dia 2 não é só bloquear propaganda, é fechar as portas de rastreamento invisível (fingerprinting) e, de quebra, economizar muita memória RAM da sua máquina.

##  1. O Navegador: Por que o Brave?
Eu escolhi o Brave para essa etapa porque ele é um excelente meio-termo. Ele entrega a proteção e o isolamento que precisamos, sem quebrar os sites do seu dia a dia (já que a base dele é o Chromium, igual ao Chrome). 

Mas atenção: **a configuração padrão dele não serve para nós**. A gente precisa colocar a mão na massa e fazer o "hardening".

### O que você precisa alterar nas configurações:
* **Brave Shields (Escudos):** Muda para "Agressivo". Isso barra os rastreadores avançados sem dó.
* **Proteção contra Fingerprinting:** Coloca no modo "Estrito". Isso impede que os sites cruzem dados do seu hardware (como tamanho da tela e placa de vídeo) para te rastrear mesmo sem cookies.
* **Privacidade e Segurança:** * Desmarque "Ajude a melhorar os recursos do Brave" (Não queremos mandar nossa telemetria pra eles).
    * Desmarque "Usar serviço do Google para ajudar a resolver erros".
* **Brave Rewards:** Desativa completamente. Queremos um navegador limpo, sem scripts nativos empurrando anúncios de criptomoeda.

##  2. A Muralha: uBlock Origin
Esqueça a ideia de que o uBlock é só um "adblockzinho". Aqui no projeto, usamos ele como um firewall dinâmico para neutralizar chamadas de rede indesejadas antes da página renderizar.

### Como deixar o uBlock blindado:
Abra as configurações da extensão, vá na aba **Listas de Filtros** e garanta que essas opções estão ativadas:
. Todas as listas da seção de **Privacidade** (como a EasyPrivacy).
. A lista de **Malware domains**.
. As listas de **Incomodidades** (isso acaba com aqueles pop-ups infinitos de "aceitar cookies").

** Para os mais avançados:** Ative o "Modo de Usuário Avançado" nas configurações. Isso libera uma interface lateral onde você pode bloquear manualmente a comunicação com servidores específicos de rastreamento que tentam dar bypass nas regras padrão.

##  O Resultado Prático
Não é só sobre privacidade, é sobre performance. Cortar as requisições de scripts de terceiros faz a sua navegação ficar absurdamente mais rápida. O seu PC respira aliviado, e os painéis de telemetria das Big Techs ficam no escuro.

---

###  FAQ: Por que o Brave e não o Tor ou Mullvad?
Se você já estuda privacidade, deve estar se perguntando por que eu não recomendei navegadores focados em anonimato extremo logo de cara. A resposta se resume a uma balança: **Conforto x Privacidade**.

O objetivo do Dia 2 é construir um kit anti-rastreio para o **dia a dia**. 
* Se eu te recomendo o **Tor**, sua internet fica consideravelmente mais lenta, quebra o seu acesso ao banco e vira um inferno de resolver CAPTCHAs. 
* Se eu recomendo o **Mullvad Browser**, a proteção anti-fingerprinting dele é tão agressiva que você precisa logar de novo em todas as suas contas todo santo dia, além de quebrar sites com DRM (como Netflix e Spotify).

O Brave é o nosso Nível 1. Ele é o *drop-in replacement* perfeito: corta a telemetria comercial pesada sem transformar o uso da sua internet num ambiente hostil e frustrante. O Tor e o Mullvad são ferramentas cirúrgicas e vão entrar nos módulos do nosso projeto mais para frente.

