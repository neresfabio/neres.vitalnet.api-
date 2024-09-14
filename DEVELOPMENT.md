### 1. **Estrutura da API Compartilhada**
A API central atenderá tanto as funcionalidades de teleconsulta quanto as de gestão da ONG, com foco na escalabilidade e segurança dos dados. Ela será construída para suportar:
- **Atendimento psicológico individual** para jovens e adultos com risco suicida.
- **Gestão de psicólogos e pacientes**, incluindo cadastro e monitoramento de atendimentos.

### 2. **Principais Funcionalidades**
Aqui estão os principais recursos que a API deve oferecer para atender ambas as aplicações:

#### a) **Gerenciamento de Usuários**
- **Cadastro de psicólogos e pacientes** com informações completas, incluindo dados socioeconômicos e anamnese.
- **Controle de acesso** por meio de perfis de usuários (pacientes, psicólogos, administradores).
  - **Endpoint**: `/users` (POST, GET, PUT, DELETE).

#### b) **Teleconsulta**
- **Agendamento de consultas** com notificação para psicólogos e pacientes.
  - Suporte para até 5 psicólogos simultaneamente.
  - **Endpoint**: `/appointments` (POST, GET, PUT).
- **Histórico de atendimentos**: Registro completo de consultas realizadas.
  - **Endpoint**: `/appointments/history` (GET).

#### c) **Ficha de Anamnese**
- Registro e atualização de informações básicas dos pacientes para uso durante as consultas.
  - **Endpoint**: `/patients/anamnesis` (POST, GET, PUT).

#### d) **Relatórios**
- Envio automático de relatórios semanais para a gerente da área.
- Relatórios detalhados sobre o progresso dos pacientes e a eficiência dos atendimentos.
  - **Endpoint**: `/reports` (POST, GET).

#### e) **Vídeo e Notificações**
- **Recurso de vídeo** para teleconsultas, integrado diretamente na plataforma.
  - **Endpoint**: `/video/sessions` (POST, GET).
- **Notificações automáticas**: Lembrete 5 minutos antes da consulta e alertas de novos pacientes para o assistente social.
  - **Endpoint**: `/notifications` (POST).

#### f) **Avaliação de Satisfação**
- Ao final do tratamento, um formulário de avaliação é enviado ao paciente.
  - **Endpoint**: `/surveys/satisfaction` (POST, GET).

### 3. **Segurança e Privacidade**
- **Criptografia de dados** para garantir a integridade e a segurança das informações, conforme a **LGPD**.
- Restrições de acesso com base no perfil do usuário, como confidencialidade na visualização das fichas de anamnese.
  - **Endpoint**: `/security/access-control` (POST).

### 4. **Gestão Financeira**
- Controle financeiro integrado para gerenciar doações e recursos destinados à manutenção da ONG.
  - **Endpoint**: `/finances` (POST, GET).

### 5. **Deploy e Escalabilidade**
- **Deploy com Docker e Kubernetes** para isolar os diferentes serviços e garantir escalabilidade conforme a demanda de usuários (psicólogos e pacientes).
- **Monitoramento**: Usar ferramentas de monitoramento como Prometheus e Grafana para acompanhar a saúde dos serviços.

### 6. **Documentação e Testes**
- Utilizar **Swagger** ou **OpenAPI** para documentar todos os endpoints da API.
- Implementar testes automatizados para garantir a qualidade dos serviços.

Essa abordagem garante que a API compartilhe funcionalidades importantes entre o site de teleconsulta e o app de gestão da ONG, garantindo eficiência no desenvolvimento e segurança dos dados.
