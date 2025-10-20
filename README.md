# 1. Fundamentos da Qualidade e Design de Software

## 1.1 Princípios SOLID

### Conceito
Solid é um acrônimo para cinco princípios  de design de classes em programação, com o objetivo de tornar os projetos mais flexíveis, compreensíveis e manuteníveis.

- | S - SRP | Single Responsability (Princípio da Responsabilidade Única)
--
**Objetivo**: Uma classe deve ter um e somente um motivo para mudar, isso significa que uma classe deve ter apenas uma tarefa central, do contrário, a classe se tornará frágil. Uma mudança em um processo poderá quebrar outros.

- | O - OCP | Open Closed Principle (Princício do Aberto Fechado)
--
**Objetivo**: Entidades de software (classes, módulos, funções) devem ser abertas para extensão, mas fechadas para modificação. Isso normalmente é feito através de interfaces, classes abstratas e herança, permitindo o plugue de novos comportamentos.

- | L - LSP | Liskov Substituition Principle (Princípio da Substituição de LIskov)
--
**Objetivo**: Subtipos devem ser substituíveis por seus tipos base sem alterar a corretude do programa. Se uma classe *Filha* herda de uma classe *Pai*, uma instância de *Filha* pode ser usada em qualquer lugar onde uma instância de *Pai* é esperada, sem causar comportamentos inesperados.

- | I - ISP | Interface Segregation Principle (Princípio de Segregação de Interface)
--
**Objetivo**: Uma classe não deve ser obeigada a implementar uma interface que não irá usar. Melhor ter muitas interfaces específicas do que uma única interface genérica. Interfaces gordas (com muitos métodos) forçam as classes implementadoras a criar implementações vazias. Isso sugere um mau design.

- | D - DIP | - Dependency Inversion Principle (Princípio da Inversão de Dependência)
-- 
**Objetivo**: Módulos de açto nível não devem depender de módulos de baixo nível, ambos devem depender de abstrações. Abstrações não devem depender de detalhes, detalhes devem depender de abstrações. Isso desacopla o código, permitindo que a implementação de baixo nível seja trocada sem impactar o código de alto nível.

## 1.2. Coesão vs Acoplamento

### Conceito

- **Coesão**: Grau em que os elementos dentro de um módulo pertencem uns aos outros. Alta coesão significa que seus métodos e atributos estão fortemente relacionados e trabalham juntos para cumprir uma responsabilidade.
- **Acoplamento**: Grau de interdenpendência entre módulos. Um baixo acomplamento significa que uma mudança no módulo tem pouca ou nenhuma chance de causar um efeito em cascata e esigir mudanças em outro módulo.

### Benefícios da <u>Alta Coesão</u> e <u>Baixo Acomplamento</u>

- <u>Maior manutenbilidade:</u> mais fáceis de entender e modificar.
- <u>Maior Reutilização:</u> pois não dependem de detalhes de outros módulos.
- <u>Maior testabilidade:</u> pois não dependem de detalhes de outros módulos.
- <u>Sistema mais Robusto:</u> alterações não quebram outras partes do sistema inesperadamente.

### Malefícios da <u>Baixa Coesão</u> e <u>Alto Acoplamento</u>

- <u>Baixa manutenbilidade</u>: uma classe faz tudo é um "pesadelo" de manter.
- <u>Baixo Reuso</u>: módulos fortemente acoplados não podem ser reutilizados facilmente.
- <u>Efeito Cascata</u>: uma pequena mudança em uma classe pode forçar alterações em outras classes que dependem dela.
- <u>Baixa testabilidade</u>: pois dependem de detalhes de outras classes/módulos, tornando muitas vezes essa tarefa impossível.

## 1.3. Inversão e Injeção de Dependência

### Conceito
- **Inversão de Dependência**: Diz respeito a princípio "D" do SOLID, que estabelece que módulos de alto nível não devem dependender de módulos de baixo nível, mas sim de abstrações.
- **Injeção de Dependência**: É o padrão de projeto que implementa a *Inversão de Dependência*. Ao invés de criar suas próprias dependências usando o operador new, as dependências são injetadas de fora por um contêiner de *Injeção de Dependência* e fornecidas como parâmetros no construtor da classe, garantindo que o objeto seja criado em um estado válido.

# 2. Identificando e Corrigindo Problemas de Design

## 2.1. Maus Cheiros de Projeto (Code Smells)

### Conceito
Não são os bugs propriamente ditos, mas sim sintomas no código que indicam um problema de design mais profundo. Pistas de que o código pode ser melhorado/refatorado e merece investigação.

* **Fragilidade**: Tendência do código em quebrar em múltiplos lugares, toda vez que uma única mudança é feita. 
    * <u>**Por que ocorre?**</u>Normalmente é causada por um alto acomplamento e baixa coesão, quando uma classe tem muitas responsabilidades ou quando muitos módulos dependem de detalhes de implementação de outros.

* **Rigidez**: Dificuldade em mudar o código, porque pequenas mudanças exigem alterações em muitas partes do código
    * <u>**Por que ocorre?**</u> Devido ao alto acoplamento entre módulos e a falta de separação de responsabilidades

* **Imobilidade**: Dificuldade em reutilizar partes do código em outros sistemas
    * <u>**Por que ocorre?**</u> Quando há baixo nível de coesão ou dependências desnecessárias entre componentes.

* **Complexidade Desnecessária**: Presença de abstrações e estruturas que não são necessárias para o problema de fato.
    * <u>**Por que ocorre?**</u> "Superengenharia" e antecipação de problemas futuros.

* **Opacidade**: Quando o código é difícil de entender e sua intenção não é clara
    * <u>**Por que ocorre?**</u> Decorrencia da má nomeação, ausencia de comentários úteis e estrutura de código confusa.

