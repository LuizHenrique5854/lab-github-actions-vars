# Análise dos Logs (Passo 2)

Nos logs, dá para ver que as variáveis globais e de job funcionam em vários steps, porque têm escopo maior.

A STEP_TEMP só funciona no step em que foi criada. No passo seguinte, ela não existe mais, porque cada step roda de forma isolada.

Por isso, variáveis de um step não são compartilhadas automaticamente. Para isso, seria necessário usar o GITHUB_ENV.

# Variáveis Padrão (Passo 3)

As variáveis padrão já existem no GitHub Actions e trazem informações da execução.

No log, aparecem corretamente o usuário, o repositório e o sistema operacional.

Isso mostra que elas podem ser usadas direto, sem precisar declarar.

# Variável Dinâmica (Passo 4)

No passo 4, foi gerado um valor aleatório e salvo como BUILD_HASH usando o GITHUB_ENV.

No passo 5, esse valor foi exibido normalmente.

Isso mostra que o GITHUB_ENV permite compartilhar variáveis entre steps do mesmo job.

# Secrets e Vars (Passo 5)

A variável URL_AMBIENTE aparece normal no log.

Já o valor de API_TOKEN_PROD aparece como ***.

Isso acontece porque secrets são protegidos automaticamente pelo GitHub.

# Por que a Secret aparece como *** e a variável aparece normalmente?

Porque o GitHub oculta automaticamente valores sensíveis (secrets) nos logs. Variáveis comuns não são ocultadas.

# O Job deploy_app consegue ler a variável BUILD_VERSION criada no Job build_app? Por quê?

Não, cada job roda em um ambiente separado. As variáveis não são compartilhadas entre jobs automaticamente.
