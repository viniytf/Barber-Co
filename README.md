# 💈 Barber & Co

Sistema de agendamento online para barbearia e salão de beleza. Os clientes escolhem os serviços, o cabeleireiro e um horário livre por um link público, sem precisar criar conta. O dono acompanha a agenda do dia e os indicadores do salão em um painel protegido por login.

🌐 **Acesse o projeto**

[CLIQUE AQUI PARA ACESSAR A BARBER & CO](https://barberco.up.railway.app/)

📅 **Como agendar**

Escolha um ou mais serviços (no mínimo um), o cabeleireiro, a data e um horário livre. Informe nome e telefone e confirme. O sistema já desconta o tempo total dos serviços escolhidos e o horário de almoço.

🔑 **Acesso do painel do Dono**

* Usuário: `Dono`
* Senha: Dono123

✨ **Principais funcionalidades**

* 🗓️ Agendamento público, sem cadastro do cliente.
* ✂️ Catálogo de serviços com duração e preço próprios, com combinação de vários serviços no mesmo atendimento.
* 👥 Agenda separada por cabeleireiro, para que um horário ocupado não bloqueie o outro.
* 🕘 Expediente com horário de almoço e bloqueio automático de horários no passado.
* 🔐 Painel do dono com login protegido por token assinado, válido por 12 horas.
* 📋 Agenda do dia por cabeleireiro, com cancelamento de atendimentos.
* 📊 Gestão com indicadores de hoje, da semana e do mês: clientes, faturamento previsto, ocupação média, ticket médio, serviços mais procurados e horários de maior movimento.

🛠️ **Tecnologias utilizadas**

* React, TypeScript e Vite no frontend, com CSS próprio
* Python e FastAPI no backend
* SQLAlchemy com PostgreSQL (Supabase)
* Pytest para os testes automatizados
* Railway para hospedagem

🧪 **Regras cobertas por testes**

* Um horário só é oferecido se o serviço couber no expediente.
* Nenhum atendimento cruza o horário de almoço.
* Dois atendimentos do mesmo cabeleireiro nunca se sobrepõem, mas podem se encostar.
* Horários no passado não são oferecidos.
* Combinações de serviços somam a duração e o preço de cada um.
* Nome e telefone são validados antes de confirmar o agendamento.
* Os cálculos de ocupação, faturamento e ticket médio seguem as mesmas regras da agenda.

🎯 **Objetivo do projeto**

Construir um sistema de agendamento completo, do banco de dados à interface, com regras de negócio reais, separação de agendas entre profissionais e acesso restrito ao painel do dono.

🔒 **Privacidade e segurança**

* O painel do dono exige login. Não há cadastro público de clientes.
* Senha e chave de assinatura ficam em variáveis de ambiente, fora do código.
* Os tokens são assinados com HMAC-SHA256 e expiram em 12 horas.
* A comparação de senha é feita em tempo constante, para evitar ataques por tempo de resposta.
* Os dados dos clientes (nome e telefone) ficam visíveis apenas no painel do dono.
