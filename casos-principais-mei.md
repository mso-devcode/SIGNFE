#Casos de Uso Principais
## Gestão da Empresa
4
 
5
### UC-001 Cadastrar Dados do MEI
6
 
7
**Objetivo:** Configurar os dados fiscais da empresa.
8
 
9
**Envolve:**
10
 
11
- CNPJ
12
- CNAE
13
- Endereço
14
- Inscrição Municipal
15
- Inscrição Estadual
16
- Certificado Digital
17
 
18
### UC-002 Atualizar Dados Cadastrais
19
 
20
Permitir manutenção dos dados do MEI.
21
 
22
---
23
 
24
## Gestão de Clientes
25
 
26
### UC-003 Cadastrar Cliente
27
 
28
Pessoa Física ou Jurídica.
29
 
30
### UC-004 Consultar Cliente
31
 
32
Buscar histórico de relacionamento.
33
 
34
### UC-005 Atualizar Cliente
35
 
36
Manter cadastros válidos para emissão fiscal.
37
 
38
---
39
 
40
## Gestão de Produtos
41
 
42
### UC-006 Cadastrar Produto
43
 
44
Dados fiscais e comerciais.
45
 
46
### UC-007 Atualizar Produto
47
 
48
### UC-008 Consultar Produto
49
 
50
---
51
 
52
## Gestão de Serviços
53
 
54
### UC-009 Cadastrar Serviço
55
 
56
### UC-010 Atualizar Serviço
57
 
58
### UC-011 Consultar Serviço
59
 
60
---
61
 
62
# Emissão Fiscal
63
 
64
## NFS-e
65
 
66
### UC-012 Emitir NFS-e
67
 
68
**Fluxo Principal**
69
 
70
```text
71
Selecionar Cliente
72
↓
73
Selecionar Serviço
74
↓
75
Validar Dados
76
↓
77
Gerar Nota
78
↓
79
Transmitir
80
↓
81
Receber Autorização
82
```
83
 
84
### UC-013 Consultar NFS-e
85
 
86
### UC-014 Cancelar NFS-e
87
 
88
### UC-015 Reenviar NFS-e ao Cliente
89
 
90
---
91
 
92
## NF-e
93
 
94
### UC-016 Emitir NF-e
95
 
96
**Fluxo Principal**
97
 
98
```text
99
Selecionar Cliente
100
↓
101
Selecionar Produtos
102
↓
103
Calcular Impostos
104
↓
105
Gerar XML
106
↓
107
Assinar
108
↓
109
Transmitir à SEFAZ
110
```
111
 
112
### UC-017 Consultar NF-e
113
 
114
### UC-018 Cancelar NF-e
115
 
116
### UC-019 Carta de Correção
117
 
118
### UC-020 Reenviar NF-e
119
 
120
---
121
 
122
## NFC-e (Preparado para Evolução)
123
 
124
### UC-021 Emitir NFC-e
125
 
126
### UC-022 Cancelar NFC-e
127
 
128
---
129
 
130
# Compliance e Obrigações Governamentais
131
 
132
## Faturamento
133
 
134
### UC-023 Monitorar Limite de Faturamento
135
 
136
O sistema acompanha:
137
 
138
- Receita Mensal
139
- Receita Acumulada
140
- Percentual do Limite MEI
141
 
142
### UC-024 Alertar Excesso de Faturamento
143
 
144
Notificações automáticas.
145
 
146
---
147
 
148
## Obrigações
149
 
150
### UC-025 Acompanhar Obrigações do MEI
151
 
152
Exibir:
153
 
154
- DAS
155
- DASN-SIMEI
156
- Pendências
157
 
158
### UC-026 Gerar Relatório para Declaração Anual
159
 
160
### UC-027 Consultar Histórico Fiscal
161
 
162
---
163
 
164
# Relacionamento com Contador
165
 
166
### UC-028 Compartilhar Informações com Contador
167
 
168
### UC-029 Exportar Movimentação Fiscal
169
 
170
### UC-030 Exportar Documentos Fiscais
171
 
172
### UC-031 Consultar Faturamento Anual
173
 
174
---
175
 
176
# Comunicação
177
 
178
### UC-032 Enviar Nota por E-mail
179
 
180
### UC-033 Gerar Link de Compartilhamento
181
 
182
### UC-034 Gerar Segunda Via
183
 
184
---
185
 
186
# Segurança
187
 
188
### UC-035 Autenticar Usuário
189
 
190
### UC-036 Configurar Métodos de Autenticação
191
 
192
**Funcionalidades sugeridas:**
193
 
194
- Ativar MFA
195
- Configurar autenticação por e-mail
196
- Configurar aplicativo autenticador
197
- Recuperar acesso
198
- Gerenciar dispositivos confiáveis
199
 
200
### UC-037 Consultar Logs
201
 
202
### UC-038 Gerenciar Certificado Digital
203
 
204
---
205
 
206
# Auditoria e Governança
207
 
208
### UC-039 Registrar Operações
209
 
210
Registrar:
211
 
212
- Emissões
213
- Cancelamentos
214
- Consultas
215
- Alterações
216
 
217
### UC-040 Armazenar XML
218
 
219
### UC-041 Armazenar DANFE
220
 
221
### UC-042 Recuperar Documento Fiscal
222
 
223
---
224
 
225
# Casos de Uso Estratégicos (Diferencial Comercial)
226
 
227
> Casos normalmente ausentes em emissores simples.
228
 
229
### UC-043 Verificar Risco de Desenquadramento
230
 
231
### UC-044 Simular Faturamento Futuro
232
 
233
### UC-045 Alertar Pendências Fiscais
234
 
235
### UC-046 Dashboard Executivo do MEI
236
 
237
**Indicadores:**
238
 
239
- Receita
240
- Clientes
241
- Serviços
242
- Produtos
243
- Evolução Mensal
244
 
245
---
246
 
247
# Arquitetura Conceitual do Produto (V1)
248
 
249
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
