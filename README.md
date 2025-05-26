# 💻📱 Projeto Integrador - 2025

----

## 📘 **Descrição**

Este repositório contém o desenvolvimento do **Projeto Integrador - Análise de Soluções Integradas para Organizações** do curso de **Tecnologia em Análise e Desenvolvimento de Sistemas**.

----

## 🛠️ **Tecnologias Utilizadas**

### 🎨 **Frontend**

- 🧱 **HTML**: Estrutura básica da aplicação e marcação do conteúdo.  
- ⚙️ **JavaScript**: Lógica e interatividade da aplicação.  
- 🎨 **Tailwind CSS**: Framework CSS para estilização e design responsivo.

### 🔧 **Backend**

- 🟢 **NodeJS**: Desenvolvimento do servidor, criação de APIs, manipulação de rotas, lógica de negócios, e integração com o banco de dados para armazenamento e recuperação de dados.

### 🗂️ **Versionamento**

- 🌿 **Git**: Controle de versão distribuído, utilizado para gerenciar o código-fonte.  
- ☁️ **GitHub**: Plataforma de hospedagem de código, utilizada para armazenar e versionar o projeto.

---

## 🎯 **Objetivo do Projeto**

O objetivo principal do projeto é o desenvolvimento de um protótipo funcional de um **aplicativo móvel e Web**.  
Para isso, foi criada uma versão web da aplicação, que é responsiva e simula a experiência de uso em dispositivos móveis e web.

---

## ✅ **Funcionalidades Implementadas**

- 📱 Interface responsiva que simula a experiência de um aplicativo móvel em dispositivos de diferentes tamanhos de tela.  
- 🎨 Design moderno e atrativo, com foco na experiência do usuário.  
- 🧭 Funcionalidades básicas de navegação, simulação de interação com o usuário.  
- 🔐 Validações no backend para login, criação, edição e exclusão de conta.

---

## 🎥 **Link do vídeo apresentação do projeto**

🔗 [https://www.youtube.com/watch?v=LffwF1fW_jI](https://www.youtube.com/watch?v=LffwF1fW_jI)

---

## 🌐 **Links da Landing Page**

### 🚀 **Deploy no GitHub Pages**  
🔗 [https://rafaelbarcarol.github.io/landing_page_projeto_integrador_analise_solucoes_integradas_organizacoes_2025/](https://rafaelbarcarol.github.io/landing_page_projeto_integrador_analise_solucoes_integradas_organizacoes_2025/)

### 📂 **Repositório**  
🔗 [https://github.com/rafaelbarcarol/landing_page_projeto_integrador_analise_solucoes_integradas_organizacoes_2025](https://github.com/rafaelbarcarol/landing_page_projeto_integrador_analise_solucoes_integradas_organizacoes_2025)

---

## Como Executar o Projeto

- Certifique-se de ter o MySQL instalado e execute o script SQL fornecido para criar o banco de dados.

- No projeto: Atualize o arquivo .env com as informações de login do seu MySQL (usuário e senha).

- No terminal da aplicação, rode o comando: npm install dotenv (se ainda não tiver o pacote).

- Após instalar o dotenv, execute o comando: node index.js.

- Pronto! A aplicação estará disponível em: http://localhost:8080

Observação: É necessário ter o Node.js e o MySQL instalados na máquina para executar o projeto.

---

## 👥 **Participantes do Grupo**

- 👩‍💻 Beatriz Vilar Guimarães Pereira  
- 👨‍💻 Juliano Teruki Felippi  
- 👩‍💻 Luanna Freire Salgado 
- 👨‍💻 Pedro Henrique Ferreira Dos Santos 
- 👨‍💻 Rafael Michalofwski Barcarol

---

## **Modelo Físico do Banco de Dados**

CREATE DATABASE projetointegrador;

USE projetointegrador;


CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    senha VARCHAR(255) NOT NULL
);


CREATE TABLE profissionais (
    id INT AUTO_INCREMENT PRIMARY KEY,
    foto VARCHAR(255),
    nome VARCHAR(50),
    sobrenome VARCHAR(50),
    profissao VARCHAR(50),
    avaliacao DECIMAL(2, 1),
    anosAtuacao INT,
    clientesAtendidos INT
);

CREATE TABLE avaliacoes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    comentario TEXT,
    estrelas INT,
    profissional_id INT,
    FOREIGN KEY (profissional_id) REFERENCES profissionais(id)
);


CREATE TABLE noticias (
    id INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(255) NOT NULL,
    autor VARCHAR(100) NOT NULL,
    data VARCHAR(10) NOT NULL,
    imagem VARCHAR(255),
    detalhes TEXT NOT NULL,
    link VARCHAR(255)
);


-- Inserindo Master na tabela usuarios
INSERT INTO usuarios(nome, email, senha) VALUES
('admin', 'admin@master.com.br', 'admin');


-- Inserindo dados na tabela profissionais
INSERT INTO profissionais (foto, nome, sobrenome, profissao, avaliacao, anosAtuacao, clientesAtendidos) VALUES
('woman.jpg', 'Ana', 'Silva', 'Nutricionista', 4.8, 5, 150),
('men.jpg', 'Pedro', 'Lima', 'Nutricionista', 4.5, 3, 100),
('woman.jpg', 'Mariana', 'Costa', 'Psicólogo', 4.9, 7, 200),
('men.jpg', 'Lucas', 'Souza', 'Psicólogo', 4.6, 4, 120),
('woman.jpg', 'Julia', 'Fernandes', 'Personal Trainer', 4.8, 5, 90),
('men.jpg', 'Ricardo', 'Almeida', 'Personal Trainer', 4.7, 6, 80);

-- Inserindo dados na tabela avaliacoes
INSERT INTO avaliacoes (comentario, estrelas, profissional_id) VALUES
('Excelente profissional! Mudou minha relação com a comida.', 5, 1),
('Muito atenciosa e dedicada. Recomendo!', 4, 1),
('Mudou minha vida! Estou mais saudável.', 5, 2),
('Muito bom, mas poderia ser mais acessível.', 4, 2),
('Profissional incrível! Me ajudou muito.', 5, 3),
('Ótima abordagem e escuta ativa.', 5, 3),
('Ótima experiência, muito atencioso.', 4, 4),
('Mudou minha vida! Aconselho a todos.', 5, 4),
('Profissional sensacional, super recomendo!', 5, 5),
('Atendimento excelente, resultados visíveis.', 4, 5),
('Os treinos são desafiadores e eficientes!', 5, 6),
('Ótimo motivador, me ajudou a alcançar meus objetivos.', 4, 6);


-- Inserindo dados na tabela noticias
INSERT INTO noticias (titulo, autor, data, imagem, detalhes, link) VALUES
('Dicas para uma Alimentação Saudável', 'Nutricionista Ana Silva', '2024-11-05', 'health.jpg', 
 'Manter uma alimentação saudável é essencial para prevenir doenças e melhorar a qualidade de vida.\nInicie suas refeições com vegetais, priorize alimentos integrais e reduza o consumo de açúcar e gorduras saturadas.\n\nEstudos mostram que pequenas mudanças, como incluir frutas frescas no café da manhã e optar por lanches naturais, podem fazer uma grande diferença.\n\n*Conclusão:*\nAdotar uma dieta equilibrada é um passo importante para alcançar o bem-estar físico e mental.', 
 'dica-alimentacao-saudavel.html'),
('Importância do Exercício Físico Diário', 'Dr. Carlos Lima', '2024-11-06', 'health.jpg', 
 'A prática regular de exercícios físicos ajuda no controle do peso, melhora a circulação e reduz o risco de doenças cardíacas.\nAtividades simples, como caminhar 30 minutos por dia, podem trazer benefícios significativos.\n\nAlém disso, exercícios também favorecem a saúde mental, ajudando a combater o estresse e a ansiedade.\n\n*Análise:*\nEstabelecer uma rotina de atividades físicas é uma das melhores maneiras de cuidar do corpo e da mente.', 
 'importancia-exercicio-fisico.html'),
('Impacto do Sono na Saúde', 'Especialista Mariana Costa', '2024-11-07', 'health.jpg', 
 'Dormir bem é tão importante quanto manter uma boa alimentação e praticar exercícios.\nA privação do sono está associada a riscos de obesidade, diabetes e doenças cardiovasculares.\n\nRecomenda-se de 7 a 9 horas de sono por noite para adultos, em um ambiente silencioso e confortável.\n\n*Importância do Tema:\nA saúde do sono é uma área que requer maior atenção, especialmente em uma sociedade que valoriza o ritmo acelerado.\n\nPerspectivas Futuras:*\nPesquisas estão sendo realizadas para entender melhor os impactos do sono de qualidade em diversas áreas da saúde.', 
 'impacto-sono-saude.html');
