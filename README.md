# SIGNFE - Sistema Integrado de Gestão de Nota Fiscal Eletrônica

## Visão Geral

O SIGNFE é uma plataforma centralizada de emissão e gerenciamento fiscal desenvolvida para atender Microempreendedores Individuais (MEI), empresas prestadoras de serviços e comerciantes.

A solução permite a emissão, consulta, cancelamento, correção e armazenamento de documentos fiscais eletrônicos, integrando-se aos órgãos governamentais e aos sistemas corporativos da empresa.

---
## Objetivo
O objetivo principal do SIGNFE é simplificar a gestão operacional, fiscal e de conformidade dos Microempreendedores Individuais (MEIs) por meio de:

- Emissão simplificada de documentos fiscais;

- Monitoramento do faturamento anual em tempo real;

- Controle automatizado de obrigações tributárias;

- Gestão de múltiplos perfis de acesso;

- Compartilhamento de informações com contadores;

- Integração com serviços governamentais.

---

## Link do diagrama:

https://drive.google.com/file/d/1nUzUzjjLS660vDStvEHJ6iarW4Lu5wtZ/view?usp=sharing
---
## Relações Principais

| Origem | Relação | Destino |
|:----------:|:----------:|:----------:|
| MEI | utiliza | sistema |
| MEI | cadastra | Dados cadastrais |
| MEI | registra | Vendas/Serviços |
| MEI | registra | Despesas |
| Vendas/Serviços | geram | Documentos fiscais |
| Documentos fiscais | alimentam | Faturamento |
| Faturamento | atualiza | Controle de limite |
| Controle de limite | produz | Alertas |
| Sistema | monitora | Obrigações |
| Sistema | armazena | Documentos |
| Sistema | fornece | Informações ao contador |
| Contador | consulta | Dados do MEI |
| Contador | analisa | Relatórios |
| Sistema | integra | Serviços governamentais |
| Administrador | gerencia | Regras e usuários |

---
## Atores do Sistema

### MEI (Empreendedor)
Responsável por:
- Registrar operações comerciais;
- Emitir documentos fiscais;
- Acompanhar faturamento;
- Consultar dashboards e indicadores.
### Contador
Responsável por:
- Consultar dados do MEI;
- Analisar relatórios;
- Receber informações compartilhadas pelo sistema.
### Administrador
Responsável por:
- Gerenciar usuários e permissões;
- Parametrizar regras fiscais e vigências;
- Auditar eventos do sistema.

### Governo / Órgãos Oficiais (Ator Externo)
Responsável por:
- Receber informações e obrigações fiscais;
- Disponibilizar serviços oficiais para integração.
---
## Fronteira do Sistema
**SIGNFE - Sistema Integrado de Gestão de Nota Fiscal Eletrônica**
---
# Funcionalidades Principais
## Gestão Cadastral e Operacional
### Cadastrar e manter dados do MEI
Gerenciamento das informações cadastrais do empreendedor:
- Dados pessoais;
- CNPJ;
- CNAE;
- Endereço;
- Atividades econômicas.
### Registrar vendas, serviços e compras
Cadastro da movimentação comercial responsável por:
- Gerar registros operacionais;
- Alimentar o controle de faturamento;
- Servir de base para emissão fiscal.
---
## Faturamento e Emissão Fiscal
### Emitir documento fiscal
Permite:
- Emissão de notas fiscais;
- Emissão de comprovantes;
- Armazenamento automático dos documentos emitidos.
### Controlar faturamento
Apuração consolidada baseada em:
- Movimentações comerciais;
- Documentos fiscais emitidos.
### Acompanhar limite e projeção
Recurso que:
- Monitora o limite de faturamento do MEI;
- Realiza projeções futuras;
- Identifica riscos de desenquadramento.
---
## Conformidade e Regras
### Monitorar conformidade
Avaliação contínua das obrigações fiscais com base em:
- Regras cadastradas;
- Limites de faturamento;
- Situação tributária do usuário.
### Gerar alertas e pendências
Notificações automáticas de:
- Prazos próximos;
- Obrigações vencidas;
- Inconsistências cadastrais;
- Riscos fiscais.

---
## Análise e Comunicação
### Consultar dashboard
Visualização rápida de:
- Indicadores de faturamento;
- Obrigações fiscais;
- Situação cadastral;
- Alertas ativos.
### Gerar e consultar relatórios
Permite:
- Emissão de relatórios gerenciais;
- Consulta de documentos;
- Consulta de movimentações;
- Compartilhamento com contador.
### Integrar e consultar serviços oficiais
Comunicação e sincronização com:
- Serviços governamentais;
- Plataformas fiscais;
- Consulta de documentos oficiais.
---
## Administração e Segurança
### Gerenciar regras e vigências
Configuração de:
- Limites legais;
- Regras tributárias;
- Parâmetros de conformidade.
### Gerenciar usuários, perfis e acessos
Controle de permissões para:
- MEI;
- Contador;
- Administrador.
### Auditar eventos e histórico
 
Registro completo de:
- Logs do sistema;
- Alterações realizadas;
- Histórico de acesso.
---
# Modelo de Dados
## Principais Entidades
| Entidade | Atributos Principais | Relacionamentos |
|-----------|-----------|-----------|
| **MEI** | CNPJ, nome, endereço, CNAE, atividades, enquadramento | Possui movimentações |
| **Movimentação** | Venda, serviço, compra, data, valor, cliente/fornecedor | Origina documentos fiscais e alimenta faturamento |
| **Documento Fiscal** | Número, série, tipo, valor, status, chave/protocolo | Subsidia obrigações e alimenta faturamento |
| **Obrigação / Prazo** | Regra, vigência, prazo, status, pendência, alerta | Utilizada por relatórios e serviços oficiais |
---
# Requisitos Não Funcionais
## Segurança e Privacidade
- Conformidade com a LGPD;
- Confidencialidade das informações;
- Integridade dos dados;
- Disponibilidade dos serviços.
## Rastreabilidade e Retenção
- Controle de acesso;
- Trilha completa de auditoria;
- Políticas de backup;
- Retenção legal de documentos fiscais.
---
# Tecnologias e Integrações Futuras
O sistema deverá suportar integrações com:
- Serviços governamentais;
- Sistemas contábeis;
- APIs fiscais;
- Soluções corporativas externas.
---
## Licença
Projeto em definição.
