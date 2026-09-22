[Uploading README.md…]()
<!--
  README DO PERFIL — repositório PH-Santiago13/PH-Santiago13
  Procure por "EDITAR" para achar os 4 pontos que você deve conferir antes de publicar.
  Comentários em HTML como este não aparecem na página publicada.
-->

<h1 align="center">Paulo Henrique Santiago</h1>

<!-- EDITAR 1: esta linha é o seu posicionamento (o mesmo dos seus repositórios), não o cargo formal. Não escreva "Analista de Dados na <empresa>". -->
<p align="center">
  <b>Analista de Dados &amp; Custos Logísticos</b><br>
  Power BI · DAX · SQL · Excel avançado
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/hpaulo13/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:hpaulo669.ph@gmail.com"><img src="https://img.shields.io/badge/E--mail-D14836?logo=gmail&logoColor=white" alt="E-mail"></a>
  <img src="https://img.shields.io/badge/S%C3%A3o%20Paulo-SP-lightgrey" alt="São Paulo, SP">
</p>

---

## 👋 Sobre mim

Transformo dados operacionais em decisões. Trabalho com custos logísticos numa transportadora — KPIs de produção, conciliação de pagamentos e relatórios gerenciais — e estou em transição estruturada para Análise de Dados / BI.

Meu foco é responder perguntas de negócio com dado confiável: modelagem dimensional (Star Schema), medidas DAX e SQL para chegar ao número certo, e automação para tirar trabalho manual do caminho.

Curso Tecnólogo em Gestão Financeira (Anhembi Morumbi, conclusão prevista em 2027), o que me ajuda a conectar a análise técnica com a linguagem de quem decide. Também mantenho a [SANTIFIN](https://www.instagram.com/santi.consultorfin), uma consultoria independente de planejamento financeiro para pessoas físicas e microempresas.

<!-- EDITAR 2: nível da vaga. Se preferir não limitar, troque por "Analista de Dados / BI". -->
🎯 **Aberto a oportunidades como Analista de Dados / BI (nível júnior).**

---

## 📌 Em números

| 2,8 mi+ | ~70% | 3 |
|:---:|:---:|:---:|
| linhas de dados públicos tratadas em pipeline MySQL | menos tempo numa rotina de fechamento (6–7 h → ~2 h) | projetos publicados, ponta a ponta |

---

## 🚀 Projetos em destaque

### 🚛 Dashboard de Controle de Agregados — análise de frota

<a href="https://github.com/PH-Santiago13/dashboard-controle-agregados">
  <img src="https://raw.githubusercontent.com/PH-Santiago13/dashboard-controle-agregados/main/images/dashboard-controle-agregados.png" alt="Dashboard de Controle de Agregados em Power BI" width="640">
</a>

*Dados 100% fictícios, gerados por mim para publicar sem expor informação da empresa.*

- **Problema:** o controle de frete e margem por viagem vivia em planilhas com dezenas de colunas; a escolha do veículo para cada rota dependia da experiência de quem olhava, não de um número comparável.
- **O que construí:** modelo Star Schema (`fVIAGENS` + dimensões de caminhões, rotas e calendário), medidas DAX (margem %, variação mês a mês com `DATEADD`) e dashboard publicado no Power BI Service.
- **Resultado:** o painel mostrou que as carretas movimentam mais frete e têm a pior margem proporcional — volume não é rentabilidade.
- **Stack:** Power BI · DAX · Power Query · Star Schema

[Ver repositório →](https://github.com/PH-Santiago13/dashboard-controle-agregados)

### 💰 Dashboard Tesouro Direto — comportamento do investidor brasileiro

<a href="https://github.com/PH-Santiago13/dashboard-tesouro-direto">
  <img src="https://raw.githubusercontent.com/PH-Santiago13/dashboard-tesouro-direto/main/images/dashboard-tesouro-direto.png" alt="Dashboard Tesouro Direto em Power BI" width="640">
</a>

- **Problema:** os dados públicos do Tesouro Nacional estão em CSVs brutos — encoding quebrado, vírgula decimal e datas em texto — praticamente inutilizáveis sem tratamento.
- **O que construí:** pipeline em MySQL (camada raw em `VARCHAR` → tipagem com `STR_TO_DATE` e `CAST`/`REPLACE`) sobre 2,8 mi+ linhas; Star Schema com duas tabelas fato e dimensões conformadas; dashboard de 2 páginas em Power BI.
- **Decisão de modelagem que defendo:** a tabela de investidores ficou isolada, porque a fonte é anonimizada e não existe chave para ligar "quem comprou o quê". Forçar a relação inflaria os números.
- **Resultado:** base validada a cada etapa (contagem, amostra e teste de encoding); o Tesouro Selic domina o volume de vendas, e as taxas negativas de 2008–2013 são comportamento real de mercado, não erro de importação.
- **Stack:** MySQL 8 · SQL (CTEs, window functions) · Power BI · DAX · Star Schema

[Ver repositório →](https://github.com/PH-Santiago13/dashboard-tesouro-direto)

### ⚙️ Automação de fechamento de dezena — RPA com Python

- **Problema:** rotina 100% manual num sistema de transporte (TMS) sem API pública: extrair relatórios de três unidades, consolidar veículo por veículo e conferir valores para gerar as Ordens de Serviço de pagamento dos agregados. Levava de 6 a 7 horas por execução.
- **O que construí:** dois scripts (`preenchimento_diario.py` e `fechamento_dezena.py`) com PyAutoGUI para a interface e Pandas para os dados; credenciais fora do código com `python-dotenv`.
- **Resultado:** de 6–7 h para ~2 h por execução (**~70% menos tempo**).
- **Trade-off assumido:** automação de tela quebra se o layout do sistema mudar. Foi a solução viável sem API, e essa limitação está documentada no repositório.
- **Stack:** Python · PyAutoGUI · Pandas · python-dotenv

[Ver repositório →](https://github.com/PH-Santiago13/automacao-preenchimento-relatorios-tms)

---

## 🧰 Stack

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-blue)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white)

| Área | O que uso |
|---|---|
| Visualização e modelagem | Power BI — Star Schema, DAX, inteligência de tempo (`CALCULATE` + `DATEADD`), Power Query |
| Consulta e ETL | SQL no MySQL 8 — JOINs, CTEs, window functions, subconsultas, `LOAD DATA`, limpeza e tipagem |
| Planilhas | Excel avançado — tabelas dinâmicas, conciliação e controles de fechamento |
| Automação | Python (Pandas, PyAutoGUI) |
| Método | Do problema de negócio ao dado, do dado ao dashboard (CRISP-DM) |

**Em evolução agora:** ![Python](https://img.shields.io/badge/Python-Pandas-3776AB?logo=python&logoColor=white) com datasets reais · estatística aplicada (teste A/B, intervalo de confiança) · dialetos SQL (T-SQL e PostgreSQL)

---

## 🔭 Em construção

<!-- EDITAR 3: apague este item se preferir não antecipar. Publique só a versão com dados fictícios e depois de alinhar com seu gestor. -->
- Painel semanal e mensal (WoW/MTD) de custo logístico, com ranking de veículos por impacto — versão pública com dados fictícios.
- Dashboard do Tesouro Direto publicado no Power BI Service, com link compartilhável.

<!--
  GITHUB STATS — ATIVAR DEPOIS, quando houver mais atividade nos repositórios.
  Não use o card "Top Languages": arquivos .pbix não são lidos como código e ele mostraria Python quase 100%,
  o que contradiz o seu posicionamento em BI/SQL.

## 📊 Atividade no GitHub

<img src="https://github-readme-stats.vercel.app/api?username=PH-Santiago13&show_icons=true&hide_border=true" alt="Estatísticas do GitHub" />
-->

---

## 📫 Contato

Conversas sobre BI, custos logísticos e finanças são bem-vindas.

- 🔗 LinkedIn: [linkedin.com/in/hpaulo13](https://www.linkedin.com/in/hpaulo13/)
<!-- EDITAR 4: o e-mail fica visível para robôs de spam. Se preferir, apague esta linha e deixe só o LinkedIn. -->
- 📧 E-mail: [hpaulo669.ph@gmail.com](mailto:hpaulo669.ph@gmail.com)
