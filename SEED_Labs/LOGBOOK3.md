# Trabalho realizado na Semana #3

Vulnerabilidade : CVE-2021-21985

## Identificação

- Vulnerabilidade no programa vSphere Client da VMware que, por falta de verificação de input, permite execução de código remotamente.
- Acessível através do plug-in SAN Health Check do vCenter Server, o que permite executar comandos pela porta 443 sem restrições. 
- O plug-in descrito acima é ativado por defeito em todos os deployments do vCenter Server, quer vSAN esteja ou não a ser utilizado.

## Catalogação

- Encontrada por Ricter Z do 360 Noah Lab e reportada em 25 de maio de 2021 pela VMware num comunicado de segurança (VMSA-2021-0010).
- Tem um CVSS (Common Vulnerability Scoring System) de 9.8, ou seja, um nível de gravidade crítico. 

## Exploit

- Um agente malicioso com acesso de rede à porta 443 pode explorar este exploit para executar comandos com privilégios irrestritos no sistema operacional.
- Automação: reprodução através de 5 pedidos de cURL, uma ferramenta de linha de comandos que transfere data usando HTTP, HTTPS, IMAP, entre outros.
- Exploit de Java unsafe reflection e SSRF na VMware vCenter Server Virtual SAN Health.

## Ataques

- Até hoje, não há relatos da utilização desta vulnerabilidade.
- No entanto, fontes públicas notaram um aumento da atividade na rede em busca de servidores vulneráveis acessíveis desde a mesma.
- E ainda, é possível encontrar facilmente githubs com explicações de como fazer ataques explorando esta vulnerabilidade
