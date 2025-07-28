Sudoku Game Project

Este repositório contém a implementação de um jogo de Sudoku em Java, com duas interfaces:

Terminal (branch main): Jogo no console, lê argumentos e usa backtracking para resolver/gerar quebra-cabeças.

Gráfica (branch ui): Interface gráfica usando Swing ou JavaFX.

🚀 Roadmap do Projeto

Modelagem do Tabuleiro

Classe Board.java: armazena matriz 9×9 e métodos de leitura/impressão

Solver (Backtracking)

Solver.java: algoritmo recursivo que encontra solução válida

Generator

Generator.java: inicia de um tabuleiro completo e remove células para criar desafios

Interface de Linha de Comando

Main.java: parse dos argumentos no formato x,y;valor;fixo

Interface Gráfica (branch ui)

GUI.java: grid interativo, botões "Resolver", "Limpar", "Sair"

Testes Automatizados

JUnit: validar solver e generator

📁 Estrutura de Pastas

sudoku/
├─ .gitignore
├─ README.md
├─ pom.xml (ou build.gradle)
└─ src/
   └─ main/
      ├─ java/br/com/dio/
      │  ├─ model/
      │  │  └─ Board.java
      │  ├─ solver/
      │  │  └─ Solver.java
      │  ├─ generator/
      │  │  └─ Generator.java
      │  ├─ app/
      │  │  └─ Main.java
      └─ ui/  (branch `ui`)
         └─ GUI.java

💡 Como Rodar

Fork & Clone

git clone https://github.com/<seu-usuario>/sudoku.git
cd sudoku

Terminal (branch main)

mvn clean compile exec:java -Dexec.mainClass="br.com.dio.app.Main" \
  -Dexec.args="0,0;4,false 1,0;7,false ..."

Ou com Gradle:

gradle run --args="0,0;4,false 1,0;7,false ..."

Gráfica (branch ui)

git checkout ui
mvn clean compile exec:java -Dexec.mainClass="br.com.dio.ui.GUI"

Testes

mvn test

🔧 Arquitetura e Padrões

Backtracking: Solver busca célula vazia e testa 1–9

POO: Board encapsula estado e validações

MVC (UI): GUI interage com Board e Solver

Design: Singleton para gerador único, Factory para diferentes níveis (fácil, médio, difícil)

🎨 Diagrama UML

Veja o diagrama em Draw.io. O arquivo está em docs/uml-sudoku.drawio.

📐 Template Visual

O protótipo está em Figma:
https://www.figma.com/file/<seu-template>/Sudoku-UI
