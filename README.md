# Dia 1: Auditoria de Dados Pessoais e OSINT

A primeira etapa do kit anti-rastreio é o reconhecimento. O objetivo hoje é mapear o que a internet já sabe sobre você, identificando vazamentos de credenciais e rastreando contas antigas que foram abandonadas em servidores de terceiros.

Siga o passo a passo abaixo em ordem.

---

## 1. Checagem de Credenciais Vazadas

A maioria das invasões ocorre por meio de vazamentos de banco de dados de grandes empresas. Vamos verificar se as suas senhas estão comprometidas.

Acesse a ferramenta de auditoria [Have I Been Pwned](https://haveibeenpwned.com/).
Insira seu endereço de e-mail atual (e repita o processo para e-mails antigos).
Clique em **"pwned?"**.
**Análise do Resultado:**
   * Se a tela retornar **Verde**: Não há registros públicos de vazamento para este e-mail.
   * Se a tela retornar **Vermelha**: Role a página. O sistema listará exatamente quais serviços vazaram seus dados e o que foi exposto (senhas, telefone, histórico).

**Ação Corretiva:** Acesse imediatamente os serviços listados na tela vermelha e altere suas senhas. 

---

## 2. Rastreamento de Usuário (Sherlock)

Vamos rodar um script de OSINT (Inteligência de Fontes Abertas) chamado Sherlock. Ele fará uma varredura em mais de 300 redes sociais buscando pelo seu nome de usuário.
Se você usa Windows, precisará do Python instalado no sistema para rodar a ferramenta.
Baixe o instalador oficial:(https://www.python.org/downloads/).
Execute o instalador.
**Importante:** Na primeira tela de instalação, marque a opção **"Add python.exe to PATH"** na parte inferior. Depois, clique em "Install Now".

### Executando a Varredura no Terminal
Pressione a tecla **Windows** no seu teclado.
Digite `cmd` e pressione **Enter** para abrir o Prompt de Comando.
Copie os comandos abaixo, cole no terminal (um por vez) e pressione **Enter** após cada um:

**Comandos:** Baixa o repositório da ferramenta para o seu computador.
```bash
git clone [https://github.com/sherlock-project/sherlock.git](https://github.com/sherlock-project/sherlock.git)

 Acessa o diretório recém-baixado.
Bash
cd sherlock

Instala as dependências necessárias para o script rodar.
Bash
pip install -r requirements.txt

(Execução): Substitua a palavra SEU_USUARIO_AQUI pelo apelido ou nome de usuário que você quer investigar.
Bash
python sherlock SEU_USUARIO_AQUI

Aguarde o processo terminar. O terminal exibirá uma lista com os links diretos de todos os sites onde encontrou uma conta ativa com esse nome.
