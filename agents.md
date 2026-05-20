agents.md - Cavalheiros SPA Landing Page
🎯 Objetivo do Projeto
Desenvolver uma landing page premium para a clínica "Cavalheiros" (Estética Masculina & SPA). O design deve seguir um padrão editorial de alto luxo, inspirado em clínicas boutique (layout Bento Grid, tipografia clássica mesclada com moderna, imagens com sobreposição), mantendo máxima performance e facilidade de manutenção.

🛠️ Stack Tecnológico
Framework Principal: Astro (SSG).

Framework UI: Vue.js 3 (Composition API) para componentes interativos.

Estilização: CSS Padrão (Vanilla CSS) estritamente. Proibido o uso de Tailwind CSS. A estilização deve ser feita através de blocos <style scoped> nos arquivos .astro e .vue.

🎨 Design System e Paleta de Cores (CSS Variables)
Criar o arquivo src/styles/global.css com as variáveis abaixo:

CSS
:root {
  /* Cores Principais Cavalheiros */
  --color-marian-blue: #1A242F; /* Background principal */
  --color-antique-gold: #C5A059; /* Destaques, ícones, botões */
  --color-sophisticated-brown: #362419; /* Footer e contrastes */
  
  /* Escala de Superfícies (Baseado no layout Aurelius) */
  --surface-base: var(--color-marian-blue);
  --surface-low: rgba(255, 255, 255, 0.03); /* Fundo de cards suaves */
  --surface-high: rgba(255, 255, 255, 0.08); /* Hover states */
  
  /* Tipografia de Contraste */
  --text-on-surface: #F5F5F7; /* Títulos e textos principais */
  --text-variant: #C4C6CB; /* Subtítulos e descrições */
  --text-on-gold: #271900; /* Texto dentro de botões dourados */

  /* Espaçamentos e Grid */
  --container-max: 1200px;
  --gutter: 24px;
}
Tipografia Global (Importar do Google Fonts):

Títulos (Display/Headlines): Playfair Display (Traz o aspecto premium/editorial).

Botões e Labels (Caps): Montserrat (Para uppercase com letter-spacing).

Corpo do texto: Inter (Legibilidade limpa).

Ícones: Material Symbols Outlined.

🧩 Arquitetura de Componentes
src/pages/index.astro: Página principal que orquestra o layout.

src/layouts/Layout.astro: <head>, importação de fontes globais e reset CSS.

src/components/:

Header.astro: Barra de navegação superior (Sticky).

Hero.astro: Seção inicial com imagem de fundo e gradiente.

ServicesBento.vue (Carregar com client:visible): Grid assimétrico de serviços.

Features.astro: Bloco de diferenciais com ícones em losangos.

CtaSection.astro: Chamada final para ação com imagem de fundo.

Footer.astro: Rodapé (Fundo Marrom Sofisticado).

BottomNavMobile.vue (Carregar com client:load): Barra fixa inferior para mobile (WhatsApp / Localização).

📋 Estrutura de Conteúdo e Estilização Vanilla CSS
1. Header (Header.astro)
Estilo CSS: position: sticky; top: 0; z-index: 50; backdrop-filter: blur(12px); background-color: rgba(26, 36, 47, 0.9); border-bottom: 1px solid rgba(197, 160, 89, 0.3);. display: flex; justify-content: space-between; align-items: center; height: 80px;.

Conteúdo Esquerda: Ícone de menu (Material Symbol) + Texto "CAVALHEIROS" (Playfair Display, bold, cor --color-antique-gold).

Conteúdo Direita: Botão "AGENDAR" (Fundo --color-antique-gold, texto --text-on-gold, fonte Montserrat uppercase).

2. Hero Section (Hero.astro)
Estilo CSS: position: relative; min-height: 80vh; display: flex; flex-direction: column; justify-content: center; overflow: hidden;.

Background: Imagem de fundo absolute com object-fit: cover e opacity: 0.4. Por cima da imagem, uma div com background: linear-gradient(to top, var(--surface-base), transparent);.

Conteúdo:

Label: "CAVALHEIROS SPA" (Montserrat, uppercase, --color-antique-gold, letter-spacing: 0.1em).

Título Principal (Playfair Display, enorme): "Excelência em Cuidado Masculino".

Subtítulo: "Onde o autocuidado encontra o bem-estar masculino. Uma experiência premium e exclusiva de SPA..."

Botão CTA: "VER SERVIÇOS" (Uppercase, padronizado com padding generoso).

3. Nossos Serviços - Bento Grid (ServicesBento.vue)
Estilo CSS: Criar um grid real: display: grid; grid-template-columns: repeat(12, 1fr); gap: var(--gutter);. Cards possuem background: var(--surface-low); border-top: 1px solid rgba(197, 160, 89, 0.2);.

Efeito de Imagem: Cada card tem uma div de imagem com overflow: hidden. A imagem dentro tem transition: transform 0.7s ease;. No :hover do card, a imagem faz transform: scale(1.05);.

Layout dos Cards (Grid CSS):

Massagem Relaxante (Destaque Grande): grid-column: span 8; (Desktop). Imagem ratio 16:9. Label: "WELLNESS".

Limpeza de Pele Profunda (Vertical): grid-column: span 4; (Desktop). Imagem ratio 3:4. Label: "SKIN".

Design / Depilação (Meio Card): grid-column: span 6; (Desktop). Label: "GROOMING".

SPA Premium (Meio Card): grid-column: span 6; (Desktop). Label: "EXPERIENCE".

Nota de Design: Títulos dos cards em Playfair Display. Labels superiores com borda dourada fininha e fonte Montserrat.

4. A Experiência / Diferenciais (Features.astro)
Estilo CSS: Seção centralizada. Grid de 3 colunas.

Ícones Rotacionados (Estilo Aurelius):

Criar um container para o ícone: width: 64px; height: 64px; border: 1px solid rgba(197, 160, 89, 0.3); background: var(--surface-low); transform: rotate(45deg); display: flex; align-items: center; justify-content: center; margin: 0 auto 24px;.

O ícone (Material Symbol) dentro do container deve ter transform: rotate(-45deg); para ficar reto, na cor --color-antique-gold.

Conteúdo:

🔒 Ambiente Privativo: Discrição total e atendimento individualizado...

🩺 Profissionais Especialistas: Equipe altamente treinada...

💎 Atendimento Exclusivo: Foco total em você...

5. Chamada Final (CtaSection.astro)
Design: Imagem de fundo sutil (opacity 10%) remetendo a texturas escuras de couro ou mármore.

Conteúdo: Centralizado. Título (Playfair Display): "Pronto para elevar seu autocuidado?". Botão grande "AGENDAR HORÁRIO".

6. Rodapé (Footer.astro)
Estilo CSS: background-color: var(--color-sophisticated-brown); padding: 64px 24px; border-top: 1px solid rgba(197, 160, 89, 0.2);. Grid de 3 colunas.

Conteúdo Exato:

Cavalheiros | Estética Masculina & SPA
📍 Endereço: Rua Quinze de Novembro, 973 - Centro, Campo Grande-MS
🕒 Horário de Funcionamento:

Segunda a Sexta: 08h às 18h | Sábados: 08h às 17h
📞 Contato: [ (67) 99104-3906 ]
Redes Sociais: [Ícones SVG Instagram e LinkedIn]
© 2026 Cavalheiros SPA. Todos os direitos reservados.
Desenvolvido por DS Desenvolvimento

7. Barra de Navegação Mobile Fixa (BottomNavMobile.vue)
Estilo CSS: Esconder no Desktop (@media (min-width: 768px) { display: none; }). Para Mobile: position: fixed; bottom: 0; left: 0; width: 100%; height: 64px; background-color: var(--color-antique-gold); z-index: 50; display: flex; border-top: 1px solid rgba(0,0,0,0.1);. Adicionar um divisor vertical entre os botões (border-right).

Lembrete de layout: Adicionar um div fantasma no final da tag <body> ou main com height: 64px visível apenas no mobile para que a barra não esconda o final do footer.

Conteúdo:

Botão 1 (50% width): Link para WhatsApp parametrizado. Ícone de Chat + Texto "WHATSAPP" (text-on-gold, Montserrat uppercase, bold).

Botão 2 (50% width): Link âncora para seção de Localização/Footer. Ícone de Location + Texto "LOCALIZAÇÃO".
