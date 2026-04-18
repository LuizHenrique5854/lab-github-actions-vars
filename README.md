# Análise dos Logs

Nos logs, dá para ver que as variáveis globais e de job funcionam normalmente em vários steps, porque têm um escopo maior.

Já a STEP_TEMP só funciona no step em que foi criada. No passo seguinte, ela não existe mais, porque cada step do GitHub Actions roda de forma isolada.

Por isso, variáveis criadas dentro de um step não são automaticamente compartilhadas com os outros. Para isso, seria necessário usar o GITHUB_ENV.
