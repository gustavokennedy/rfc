# RFC: Implementação de Novo Sistema de Autenticação com OAuth2

**Data de criação:** 2024-11-10  
**Autor:** Gustavo Kennedy Renkel  
**Status:** Em Discussão  
**Data da última atualização:** 2024-11-10  

---

## Contexto

O sistema atual de autenticação da aplicação é baseado em login com nome de usuário e senha, sem suporte para login social ou single sign-on (SSO). Para aprimorar a segurança e melhorar a experiência do usuário, estamos propondo a implementação de um novo sistema de autenticação utilizando o protocolo OAuth2, que permitirá autenticação com provedores externos, como Google e Facebook.

## Problema

O sistema de autenticação atual apresenta as seguintes limitações:
- Não oferece suporte a SSO.
- Dificuldade em implementar autenticação multifatorial (MFA).
- Requer que os usuários criem e gerenciem senhas específicas para nossa aplicação, o que reduz a experiência do usuário.

Essas limitações dificultam a escalabilidade e a integração com serviços corporativos que usam autenticação unificada.

## Solução Proposta

Implementar um novo sistema de autenticação baseado em OAuth2. A proposta consiste em:

1. **Integrar com Provedores de OAuth2**: Permitir autenticação via Google e Facebook.
2. **Autenticação Unificada (SSO)**: Usar OAuth2 para permitir SSO em sistemas corporativos.
3. **Configuração de Permissões Granulares**: Controlar escopos e permissões de acesso aos dados.

### Passos de Implementação

1. Selecionar uma biblioteca OAuth2 confiável para a integração.
2. Configurar credenciais e escopos de acesso com Google e Facebook.
3. Implementar o fluxo de autenticação e autorização na aplicação.
4. Ajustar a interface de login para incluir as opções de login social.
5. Criar documentação e treinar a equipe de suporte.

### Arquitetura Proposta

- **Frontend**: Botões para login social e SSO com Google/Facebook.
- **Backend**: Endpoints para gerenciar o fluxo OAuth2 e emitir tokens de acesso.
- **Banco de Dados**: Armazenamento seguro dos tokens OAuth2 e controle de sessão.

## Impacto

Essa mudança terá impacto nas seguintes áreas:

- **Experiência do Usuário**: Os usuários terão uma experiência de login mais simples e segura.
- **Segurança**: A segurança será aprimorada com o uso de tokens de curta duração e autenticação multifatorial via provedores externos.
- **Manutenção**: O novo sistema exigirá manutenção periódica para garantir a compatibilidade com as APIs dos provedores.

## Riscos e Considerações

- **Dependência de Provedores Externos**: Falhas nos serviços do Google ou Facebook podem impactar os logins.
- **Compatibilidade**: É necessário garantir que o novo sistema de autenticação seja compatível com o sistema legado durante o período de transição.

## Alternativas Consideradas

1. **Manter o sistema atual**: Menos custos iniciais, mas com poucas melhorias em segurança e experiência do usuário.
2. **Implementar SSO Interno**: Custos elevados de desenvolvimento e manutenção.

## Cronograma

| Fase                  | Data de Início | Data de Conclusão | Responsável        |
|-----------------------|----------------|--------------------|--------------------|
| Pesquisa e Planejamento | 15-11-2024    | 30-11-2024        | Gustavo Kennedy Renkel         |
| Desenvolvimento       | 01-12-2024    | 15-01-2025        | [Nome Responsável]  |
| Testes e QA          | 16-01-2025    | 01-02-2025        | [Nome Responsável]       |
| Lançamento           | 02-02-2025    | 08-02-2025        | [Nome Responsável]   |

## Aprovação

**Aprovadores**  
- [Nome Responsável]

---
