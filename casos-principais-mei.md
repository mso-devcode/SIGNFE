# Casos de Uso Principais
## Gestão da Empresa
### UC-001 Cadastrar Dados do MEI
**Objetivo:** Configurar os dados fiscais da empresa.
**Envolve:**
- CNPJ
- CNAE
- Endereço
- Inscrição Municipal
- Inscrição Estadual
- Certificado Digital

## UC-002 Atualizar Dados Cadastrais
 - Permitir manutenção dos dados **MEI**
---
# Gestão de Clientes
### UC-003 Cadastrar Cliente
- Pessoa Física ou Jurídica.
### UC-004 Consultar Cliente
- Buscar histórico de relacionamento.

### UC-005 Atualizar Cliente
- Manter cadastros válido para emissão fiscal.
---
## Gestão de Produtos
### UC-006 Cadastrar Produto
Dados fiscais e comerciais.
### UC-007 Atualizar Produto
### UC-008 Consultar Produto
---
## Gestão de Serviços
### UC-009 Cadastrar Serviço
### UC-010 Atualizar Serviço
### UC-011 Consultar Serviço
---
# Emissão Fiscal
## NFS-e
### UC-012 Emitir NFS-e
**Fluxo Principal**
```mermaid
flowchart TD
    
    A((Início))
    B[Selecionar Cliente]
    C[Selecionar Serviço]
    D[Validar Dados]
    E[Gerar Nota]
    F[Transmitir]
    G[Receber Autorização]
    H((Fim))
     
    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
```
### UC-013 Consultar NFS-e
### UC-014 Cancelar NFS-e
### UC-015 Reenviar NFS-e ao Cliente
---
## NF-e
### UC-016 Emitir NF-e
**Fluxo Principal**
```mermaid
flowchart TD
    
    A((Início))
    B[Selecionar Cliente]
    C[Selecionar Produtos]
    D[Calcular Impostos]
    E[Gerar XML]
    F[Assinar XML]
    G[Transmitir à SEFAZ]
    H((NF-e Autorizada))
     
    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
```
### UC-017 Consultar NF-e
### UC-018 Cancelar NF-e
### UC-019 Carta de Correção
### UC-020 Reenviar NF-e
---
## NFC-e (Preparado para Evolução)
### UC-021 Emitir NFC-e
### UC-022 Cancelar NFC-e
---
# Compliance e Obrigações Governamentais
## Faturamento
### UC-023 Monitorar Limite de Faturamento
O sistema acompanha:
- Receita Mensal
- Receita Acumulada
- Percentual do Limite MEI
### UC-024 Alertar Excesso de Faturamento
Notificações automáticas.
---
## Obrigações
### UC-025 Acompanhar Obrigações do MEI
Exibir:
- DAS
- DASN-SIMEI
- Pendências
### UC-026 Gerar Relatório para Declaração Anual
### UC-027 Consultar Histórico Fiscal
---
# Relacionamento com Contador
### UC-028 Compartilhar Informações com Contador
### UC-029 Exportar Movimentação Fiscal
### UC-030 Exportar Documentos Fiscais
### UC-031 Consultar Faturamento Anual
---
# Comunicação
### UC-032 Enviar Nota por E-mail
### UC-033 Gerar Link de Compartilhamento
### UC-034 Gerar Segunda Via
---
# Segurança
### UC-035 Autenticar Usuário
### UC-036 Configurar Métodos de Autenticação
**Funcionalidades sugeridas:**
- Ativar MFA
- Configurar autenticação por e-mail
- Configurar aplicativo autenticador
- Recuperar acesso
- Gerenciar dispositivos confiáveis
### UC-037 Consultar Logs
### UC-038 Gerenciar Certificado Digital
---
# Auditoria e Governança
### UC-039 Registrar Operações
Registrar:
- Emissões
- Cancelamentos
- Consultas
- Alterações
 
### UC-040 Armazenar XML
### UC-041 Armazenar DANFE
### UC-042 Recuperar Documento Fiscal
---
# Casos de Uso Estratégicos (Diferencial Comercial)
> Casos normalmente ausentes em emissores simples.
### UC-043 Verificar Risco de Desenquadramento
### UC-044 Simular Faturamento Futuro
### UC-045 Alertar Pendências Fiscais
### UC-046 Dashboard Executivo do MEI
**Indicadores:**
- Receita
- Clientes
- Serviços
- Produtos
- Evolução Mensal
---
# Arquitetura Conceitual do Produto (V1)
```text
250
MEI
251
│
252
├── Gestão da Empresa
253
│ ├── UC-001 Cadastrar Empresa
254
│ └── UC-002 Atualizar Empresa
255
│
256
├── Clientes
257
│ ├── UC-003 Cadastrar Cliente
258
│ ├── UC-004 Consultar Cliente
259
│ └── UC-005 Atualizar Cliente
260
│
261
├── Produtos e Serviços
262
│ ├── UC-006 Cadastrar Produto
263
│ ├── UC-009 Cadastrar Serviço
264
│ └── Manutenção
265
│
266
├── Fiscal
267
│ ├── UC-012 Emitir NFS-e
268
│ ├── UC-016 Emitir NF-e
269
│ ├── UC-021 Emitir NFC-e
270
│ ├── Cancelar
271
│ ├── Corrigir
272
│ └── Consultar
273
│
274
├── Compliance
275
│ ├── UC-023 Monitorar Limite MEI
276
│ ├── UC-024 Alertar Excesso
277
│ ├── UC-025 Obrigações
278
│ └── UC-026 DASN-SIMEI
279
│
280
├── Contador
281
│ ├── UC-028 Compartilhar Dados
282
│ ├── UC-029 Exportar Fiscal
283
│ └── UC-030 Exportar XML
284
│
285
├── Comunicação
286
│ ├── UC-032 Enviar Nota
287
│ ├── UC-033 Compartilhar Link
288
│ └── UC-034 Segunda Via
289
│
290
└── Governança
291
├── UC-035 Login
292
├── UC-036 MFA
293
├── UC-039 Auditoria
294
├── UC-040 Armazenamento
295
└── UC-042 Recuperação
296
```
297
 
298
## Visão Geral
299
 
300
A arquitetura foi concebida para cobrir integralmente o ciclo operacional do MEI:
301
 
302
- Operação do negócio
303
- Emissão fiscal
304
- Conformidade governamental
305
- Relacionamento com contador
306
- Segurança
307
- Governança
308
 
309
Além disso, mantém a solução preparada para futuras expansões funcionais.
