# Dia 3: Blindagem de Senhas (Zero-Knowledge)

Salvar senhas no próprio navegador (Chrome, Edge, Safari) é o erro de segurança mais comum e perigoso que existe. O banco de dados do navegador é um alvo fácil: um script malicioso básico consegue extrair todas as suas senhas em segundos.

A regra para blindar sua vida digital é a **Criptografia de Conhecimento Zero**. Isso significa que vamos usar um cofre onde a criptografia acontece na sua máquina. A empresa que guarda o cofre (vamos usar o Bitwarden, que é código aberto) não tem a chave para abri-lo. Se eles forem invadidos, os hackers só levam um texto embaralhado.

Siga o passo a passo rigorosamente.

---

##  Passo 1: Exportar as senhas antigas do Navegador

Vamos tirar suas senhas do alvo fácil. Vou usar o Google Chrome como exemplo, pois é o mais comum:

. Abra o Chrome no seu computador.
. Clique nos **três pontinhos** no canto superior direito e vá em **Configurações**.
. No menu lateral esquerdo, clique em **Preenchimento automático e senhas** e depois em **Gerenciador de senhas do Google**.
. Clique em **Configurações** (no menu lateral do gerenciador).
. Role a página até achar a opção **Exportar senhas** e clique no botão para exportar.
. O computador vai pedir a senha que você usa para ligar o Windows/Mac (para confirmar que é você).
. Ele vai gerar um arquivo chamado `Senhas do Google.csv`. Salve na sua Área de Trabalho.

 **ALERTA MÁXIMO:** Esse arquivo `.csv` contém todas as suas senhas em texto puro, abertas para qualquer um ler. Não envie para ninguém e não o perca de vista. Vamos destruí-lo no Passo 4.

---

##  Passo 2: Criando o seu Cofre (Bitwarden)

. Acesse o site oficial: [bitwarden.com](https://bitwarden.com/).
. Clique em **Get Started** (ou Começar) para criar uma conta gratuita.
. Preencha seu e-mail.
. **A Senha Mestra (O passo mais importante da sua vida digital):**
   * Você vai criar uma única senha para trancar esse cofre. Essa é a única senha que você precisará decorar a partir de hoje.
   * Crie uma frase longa, misturando letras maiúsculas, números e símbolos (Ex: `M3uCachorroMordeuOCarteiroEm2015!`).
   * **Aviso definitivo:** O Bitwarden NÃO tem a opção "Esqueci minha senha". Se você esquecer essa senha mestra, ninguém no mundo consegue recuperar suas contas. Escreva ela em um papel físico por enquanto e guarde na sua gaveta.

---

##  Passo 3: Importando suas senhas para o Cofre

. Faça o login no site do Bitwarden que você acabou de criar. Essa é a sua "Caixa-Forte Web".
. No menu superior, clique em **Ferramentas** (Tools).
. No menu lateral, clique em **Importar Dados** (Import Data).
. No primeiro campo (Formato), escolha **Chrome (csv)**.
. No segundo campo, clique em **Escolher arquivo** e selecione aquele arquivo `Senhas do Google.csv` que salvamos na Área de Trabalho.
. Clique no botão **Importar Dados**.
. Pronto. Suas senhas agora estão dentro do cofre blindado.

---

##  Passo 4: Queimando as pontes (Obrigatório)

Agora que as senhas estão seguras, precisamos eliminar as vulnerabilidades antigas.

. **Destrua o arquivo:** Vá na sua Área de Trabalho, clique com o botão direito no arquivo `Senhas do Google.csv` e exclua. Depois, vá na Lixeira do computador e esvazie ela. 
. **Desative o Chrome:** Volte lá no Gerenciador de Senhas do Chrome (onde fomos no Passo 1).
. Desmarque a opção **Oferecer para salvar senhas** e desmarque o **Login automático**. O Chrome não deve mais se intrometer nas suas credenciais.
. Delete as senhas que ficaram salvas no painel do Chrome.

---

##  Passo 5: Como usar no dia a dia

O cofre só é útil se for prático.

. **No Computador:** Instale a **Extensão do Bitwarden** na loja do seu navegador. Ela vai ficar como um ícone de escudo azul do lado da barra de endereços. Sempre que você entrar num site, ela vai preencher a senha para você automaticamente.
. **No Celular:** Baixe o aplicativo do Bitwarden (tem na App Store para o seu iPhone ou na Play Store se usar Android). Vá nas configurações do celular e defina o Bitwarden como o "Preenchedor Automático de Senhas" padrão.

A partir de hoje, sempre que for criar uma conta nova em algum site, abra a extensão do Bitwarden e clique no ícone de "+" para gerar uma string aleatória de 20 caracteres. 

## Opinião tecnica (Leitura Avançada)
Se você é da área de cibersegurança ou simplesmente quer entender como a matemática por trás da Criptografia de Conhecimento Zero garante que o Bitwarden não consiga ler seus dados, preparei um relatório técnico dissecando a arquitetura da ferramenta, posso estar equivocado em algumas coisas la, analisei 3 fontes que esta no relatorio.

👉 [Ler a Análise Técnica de Arquitetura e Criptografia do Bitwarden](./analise-tecnica-bitwarden.md)

Nos vemos no Dia 4.
