# Princípios SOLID de Design com Exemplos de Padrões de Projeto

SOLID é um conjunto de princípios na programação orientada a objetos que ajuda a criar software mais manutenível, flexível e compreensível. Este repositório fornece explicações e exemplos de cada princípio SOLID juntamente com implementações de padrões de projeto.

## Princípio da Responsabilidade Única (SRP)

Uma classe deve ter apenas um motivo para mudar. Ela deve ter uma única responsabilidade.

**Exemplo**: A classe "Usuário" deve ser responsável apenas por gerenciar os dados do usuário, não por enviar e-mails. Separe a funcionalidade de envio de e-mails em uma classe separada, como "EmailSender".

## Princípio do Aberto/Fechado (OCP)

As entidades de software devem estar abertas para extensão, mas fechadas para modificação. Nova funcionalidade pode ser adicionada sem alterar o código existente.

**Exemplo**: Use o padrão de projeto "Strategy" para definir diferentes algoritmos de processamento de pagamentos. Adicionar um novo método de pagamento não requer modificar o código existente de processamento de pagamentos.

## Princípio da Substituição de Liskov (LSP)

Subtipos devem ser substituíveis por seus tipos base sem afetar a correção do programa.

**Exemplo**: Se você tem uma classe base "Forma" com um método "calcularArea()", qualquer subclasse (como "Círculo" ou "Retângulo") deve implementar esse método conforme o esperado.

## Princípio da Segregação de Interface (ISP)

Clientes não devem ser forçados a depender de interfaces que não utilizam. Mantenha as interfaces focadas e específicas.

**Exemplo**: Ao invés de uma interface monolítica "Trabalhador", divida-a em interfaces menores como "Trabalhador" (com métodos comuns) e "Comedor" (com métodos relacionados a comer).

## Princípio da Inversão de Dependência (DIP)

Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações. Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.

**Exemplo**: Use injeção de dependência para passar dependências (como conexões de banco de dados) para uma classe em vez de codificá-las diretamente. Isso torna mais fácil trocar implementações sem modificar a classe.

## Exemplos de Padrões de Projeto

Este repositório inclui implementações de padrões de projeto para cada princípio SOLID:

- SRP: **Princípio da Responsabilidade Única** com *Padrão Observer*
- OCP: **Princípio do Aberto/Fechado** com *Padrão Strategy*
- LSP: **Princípio da Substituição de Liskov** com *Padrão Template Method*
- ISP: **Princípio da Segregação de Interface** com *Padrão Adapter*
- DIP: **Princípio da Inversão de Dependência** com *Injeção de Dependência*

Cada diretório de padrão contém exemplos de código, explicações e diagramas ilustrando como o padrão aborda o princípio SOLID correspondente.

Sinta-se à vontade para explorar cada diretório para entender como esses princípios podem ser aplicados em cenários do mundo real.

## Contribuições

Contribuições, correções e sugestões são bem-vindas! Se você encontrar algum problema ou quiser adicionar mais exemplos, fique à vontade para abrir um pull request.
