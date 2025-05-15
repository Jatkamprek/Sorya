**Contrato de Dados — Plataforma de Gestão de Pacientes com IA**

Este contrato de dados define os principais modelos de dados utilizados pela plataforma de gestão de pacientes com suporte de IA, organizados por módulos e funcionalidades.

---

### ✅ **Usuário**

```json
{
  "id": "uuid",
  "nomeCompleto": "string",
  "email": "string",
  "senhaHash": "string",
  "numeroCRFa": "string",
  "papel": "enum: [pendente, profissional, administrador]",
  "termosAceitos": true,
  "criadoEm": "datetime",
  "atualizadoEm": "datetime"
}
```

### 📅 **Sessão Clínica**

```json
{
  "id": "uuid",
  "pacienteId": "uuid",
  "profissionalId": "uuid",
  "dataHora": "datetime",
  "objetivo": "string",
  "itensUtilizados": ["string"],
  "descricao": "string",
  "criadoEm": "datetime"
}
```

### 🧑‍⚕️ **Paciente**

```json
{
  "id": "uuid",
  "profissionalId": "uuid",
  "nome": "string",
  "idade": "number",
  "sexo": "enum: [masculino, feminino, outro]",
  "diagnostico": "string",
  "queixaPrincipal": "string",
  "criadoEm": "datetime",
  "atualizadoEm": "datetime"
}
```

### 🔄 **Planejamento Terapêutico**

```json
{
  "id": "uuid",
  "pacienteId": "uuid",
  "profissionalId": "uuid",
  "geradoPorIA": true,
  "objetivoGeral": "string",
  "objetivosEspecificos": ["string"],
  "sugestaoDeAtividades": ["string"],
  "criadoEm": "datetime",
  "atualizadoEm": "datetime"
}
```

### 📄 **Relatório**

```json
{
  "id": "uuid",
  "pacienteId": "uuid",
  "profissionalId": "uuid",
  "tipo": "enum: [protocolo, geral]",
  "conteudo": "string",
  "geradoPorIA": true,
  "pdfUrl": "string",
  "criadoEm": "datetime"
}
```

### 📃 **Mídia/Transcrição**

```json
{
  "id": "uuid",
  "pacienteId": "uuid",
  "profissionalId": "uuid",
  "tipo": "enum: [audio, texto]",
  "arquivoUrl": "string",
  "transcricao": "string",
  "integradoAoRelatorio": true,
  "criadoEm": "datetime"
}
```

### 💳 **Assinatura/Plano**

```json
{
  "id": "uuid",
  "usuarioId": "uuid",
  "tipo": "enum: [mensal, anual]",
  "status": "enum: [ativo, cancelado, inadimplente]",
  "stripeCustomerId": "string",
  "stripeSubscriptionId": "string",
  "inicio": "datetime",
  "fim": "datetime"
}
```

### 📢 **Suporte/Contato**

```json
{
  "id": "uuid",
  "usuarioId": "uuid",
  "tipo": "enum: [email, whatsapp]",
  "mensagem": "string",
  "respondido": true,
  "criadoEm": "datetime"
}
```

---

**Observações Gerais:**

* Todos os IDs seguem o padrão UUID.
* Datas devem ser armazenadas em formato ISO 8601.
* Campos sensíveis como "senhaHash" devem ser criptografados.
* Controle de acesso deve garantir que dados só sejam acessados por usuários autorizados.

Se desejar, posso gerar a estrutura de tabelas SQL com base neste contrato ou os tipos TypeScript correspondentes.
