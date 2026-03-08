# 🌿 Projeto Jardim Secreto

Um site de rede social temático com design inspirado na natureza, criado para compartilhamento de conteúdo com sistema de permissões diferenciadas.

## 📋 Visão Geral

O **Projeto Jardim Secreto** é uma plataforma de rede social leve e aconchegante, com estética natural em tons verdes. O site oferece dois tipos de acesso: usuários convidados (apenas visualização e interação) e desenvolvedores/professores (acesso completo com permissões de criação e moderação).

## ✨ Funcionalidades Implementadas

### 🔐 Sistema de Login Duplo
- **Convidado/Usuário**: 
  - Acesso sem senha, apenas com nome de usuário
  - Pode visualizar todos os posts
  - Pode curtir (👍) e não curtir (👎) posts
  - Pode comentar em posts
  - Pode curtir/não curtir comentários
  
- **Desenvolvedor/Professor**:
  - Requer e-mail Gmail e senha específica: `#################` (censurado)
  - Todas as permissões de convidado +
  - Pode criar novos posts com título, descrição e imagem
  - Pode excluir qualquer post
  - Pode excluir qualquer comentário
  - Badge especial "🏴 Criador" quando comenta no próprio post

### 📱 Interface de Rede Social
- Feed de posts estilo Instagram/Facebook
- Design responsivo e mobile-friendly
- Paleta de cores em tons de verde (verde musgo, floresta, menta, oliva)
- Decorações flutuantes de folhas e plantas (🍃 🌿 🍀 🌱 🌾)
- Animações suaves e transições elegantes
- Header fixo com logo e informações do usuário

### 📝 Sistema de Posts
- **Criar Post** (apenas Desenvolvedores/Professores):
  - Campo de título
  - Campo de descrição
  - Opção 1: Colar URL de imagem externa
  - Opção 2: Upload de imagem do dispositivo (base64)
  - Preview da imagem antes de publicar
  
- **Visualizar Posts**:
  - Título em destaque com fonte Playfair Display
  - Descrição completa
  - Imagem (se adicionada)
  - Nome do autor e data de publicação
  - Contador de curtidas e não curtidas
  - Contador de comentários

### 👍 Sistema de Curtidas
- Botões de 👍 Gostei e 👎 Não Gostei em posts
- Contadores em tempo real
- Mesma funcionalidade para comentários
- Visual diferenciado quando o usuário já curtiu/não curtiu
- Possibilidade de remover curtida clicando novamente

### 💬 Sistema de Comentários
- Seção de comentários expansível em cada post
- Campo para escrever e enviar comentário
- Badge especial "🏴 Criador" para autor do post
- Curtir/não curtir cada comentário individualmente
- Botão de excluir (apenas para Desenvolvedores/Professores)
- Data e hora relativas ("5m atrás", "2h atrás", etc.)

### 🗄️ Banco de Dados (localStorage)
Estruturas de dados persistentes:
- **jardim_posts**: Array com todos os posts
- **jardim_comments**: Array com todos os comentários
- **jardim_likes**: Array com curtidas de posts e comentários
- **jardim_session**: Sessão do usuário atual

Campos dos Posts:
```javascript
{
  id: string,
  title: string,
  description: string,
  image: string (URL ou base64),
  author: string,
  authorType: 'guest' | 'developer',
  date: ISO string,
  likes: number,
  dislikes: number
}
```

Campos dos Comentários:
```javascript
{
  id: string,
  postId: string,
  author: string,
  authorType: 'guest' | 'developer',
  text: string,
  date: ISO string
}
```

### 🎨 Design e Decorações
- **Paleta de Cores**:
  - Verde Escuro: `#2d5016`
  - Verde Médio: `#4a7c2e`
  - Verde Floresta: `#3d6b2e`
  - Verde Musgo: `#6b8e4e`
  - Verde Menta: `#a8d5ba`
  - Verde Claro: `#d4edda`
  - Verde Suave: `#e8f5e9`

- **Elementos Decorativos**:
  - Folhas flutuantes animadas no fundo
  - Gradientes suaves verde-natureza
  - Bordas arredondadas em todos os cards
  - Sombras suaves e elegantes
  - Animações de hover nos botões

- **Tipografia**:
  - Títulos: Playfair Display (serif elegante)
  - Corpo: Lato (sans-serif moderna)

## 🚀 Como Usar

### Acesso ao Site
1. Abra o arquivo `index.html` no navegador
2. Escolha o tipo de login:

**Opção 1 - Como Convidado:**
```
1. Clique em "🌱 Convidado / Usuário"
2. Digite um nome de usuário
3. Clique em "Entrar 🌿"
```

**Opção 2 - Como Desenvolvedor/Professor:**
```
1. Clique em "🌳 Desenvolvedor / Professor"
2. Digite um e-mail do Gmail (ex: seuemail@gmail.com)
3. Digite a senha: JARDIMSECRETO2015
4. Clique em "Entrar 🌿"
```

### Criar um Post (Desenvolvedores/Professores)
```
1. Clique no botão "✨ Criar Novo Post"
2. Preencha o título
3. Escreva a descrição
4. Adicione uma imagem:
   - Cole a URL de uma imagem OU
   - Selecione uma imagem do seu dispositivo
5. Clique em "Publicar 🌿"
```

### Interagir com Posts
```
- Curtir/Não Curtir: Clique nos botões 👍 ou 👎
- Comentar: Clique em "💬 Comentários", escreva e envie
- Excluir (apenas Dev/Prof): Clique no botão "🗑️ Excluir"
```

## 📂 Estrutura do Projeto

```
projeto-jardim-secreto/
├── index.html          # Arquivo principal (HTML + CSS + JavaScript)
└── README.md           # Este arquivo
```

## 🔒 Credenciais de Acesso

### Desenvolvedor/Professor
- **E-mail**: Qualquer e-mail @gmail.com
- **Senha**: `JARDIMSECRETO2015`

### Convidado/Usuário
- **Credencial**: Apenas um nome de usuário (sem senha)

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura semântica
- **CSS3**: Estilização com variáveis CSS, flexbox, animações
- **JavaScript ES6+**: Lógica da aplicação, manipulação do DOM
- **localStorage**: Banco de dados persistente no navegador
- **Google Fonts**: Playfair Display e Lato

## 🌟 Recursos Técnicos

### Persistência de Dados
- Todos os dados são salvos no localStorage do navegador
- Sessão de login persistente (mantém login após recarregar página)
- Histórico completo de posts, comentários e curtidas

### Responsividade
- Layout adaptável para desktop, tablet e mobile
- Breakpoint principal: 768px
- Fontes e espaçamentos ajustáveis

### Performance
- Arquivo único (sem dependências externas além de fonts)
- Imagens podem ser carregadas por URL (otimizado) ou base64 (dispositivo)
- Animações otimizadas com CSS

## 📱 URIs Funcionais

### Página Principal
```
index.html
```

### Funcionalidades JavaScript
```javascript
// Login
loginAsGuest()              // Login como convidado
loginAsDeveloper()          // Login como desenvolvedor/professor
logout()                    // Fazer logout

// Posts
createPost()                // Criar novo post
deletePost(postId)          // Excluir post
loadPosts()                 // Carregar todos os posts
likePost(postId, type)      // Curtir/não curtir post

// Comentários
addComment(postId)          // Adicionar comentário
deleteComment(commentId)    // Excluir comentário
likeComment(commentId, postId, type)  // Curtir/não curtir comentário
toggleComments(postId)      // Mostrar/ocultar comentários
```

## 🎯 Funcionalidades Não Implementadas

Nenhuma funcionalidade pendente - todas as solicitações foram implementadas! ✅

## 🔮 Próximos Passos Recomendados

### Melhorias Sugeridas
1. **Sistema de Perfis**
   - Página de perfil para cada usuário
   - Avatar personalizado
   - Biografia e informações adicionais

2. **Busca e Filtros**
   - Buscar posts por título ou descrição
   - Filtrar por autor
   - Ordenar por data ou popularidade

3. **Notificações**
   - Notificar quando alguém comenta no seu post
   - Notificar quando recebe curtidas
   - Badge de novas interações

4. **Editor de Posts**
   - Editar posts já publicados
   - Editar comentários
   - Formatação rica (negrito, itálico, links)

5. **Categorias e Tags**
   - Adicionar categorias aos posts (Natureza, Dicas, Curiosidades, etc.)
   - Sistema de hashtags
   - Filtro por categoria

6. **Compartilhamento**
   - Compartilhar posts nas redes sociais
   - Gerar link direto para post específico
   - Embed de posts

7. **Moderação Avançada**
   - Sistema de denúncias
   - Usuários banidos
   - Log de ações de moderação

8. **Estatísticas**
   - Dashboard para desenvolvedores
   - Métricas de engajamento
   - Posts mais populares

9. **Acessibilidade**
   - Melhorar suporte a leitores de tela
   - Atalhos de teclado
   - Alto contraste opcional

10. **Tema Escuro**
    - Modo noturno com tons de verde escuro
    - Toggle entre modo claro/escuro
    - Preferência salva no localStorage

## 💡 Dicas de Uso

### Para Desenvolvedores/Professores
- Use imagens com boa qualidade mas não muito pesadas
- Escreva títulos chamativos e descritivos
- Modere comentários inadequados usando o botão de exclusão
- Crie posts regulares para manter a comunidade ativa

### Para Convidados/Usuários
- Seja respeitoso nos comentários
- Curta posts que você gostar para dar feedback
- Participe ativamente comentando e interagindo

### Gerenciar Dados
Para limpar todos os dados e recomeçar do zero, abra o Console do navegador (F12) e execute:
```javascript
localStorage.clear();
location.reload();
```

## 🐛 Solução de Problemas

### Login não funciona
- Verifique se está usando um e-mail @gmail.com
- Confirme que a senha é exatamente: `JARDIMSECRETO2015` (maiúsculas)
- Limpe o cache do navegador se necessário

### Posts não aparecem
- Verifique se há posts criados (desenvolvedores)
- Tente recarregar a página
- Verifique o Console do navegador (F12) para erros

### Imagens não carregam
- Verifique se a URL da imagem está correta e acessível
- Para upload local, use apenas arquivos de imagem (JPG, PNG, GIF)
- Imagens muito grandes podem demorar para carregar

## 📄 Licença

Este projeto foi criado para fins educacionais e de demonstração.

## 👨‍💻 Autor

Desenvolvido com 💚 e muita natureza!

---

**Versão**: 1.0.0  
**Data**: 2026-03-08  
**Status**: ✅ Totalmente Funcional

🌿 Bem-vindo ao Jardim Secreto! 🌿
