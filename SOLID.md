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


## Codigo

# Princípio da Responsabilidade Única (SRP)
Exemplo: Uma classe que lida com leitura de arquivos CSV e cálculos estatísticos.

```php
class LeitorCSV {
    public function lerArquivo($caminho) {
        // Lê o arquivo CSV
    }
}

class CalculadoraEstatistica {
    public function calcularMedia($dados) {
        // Calcula a média dos dados
    }
}
```php

Padrão de Projeto Associado: Nenhum padrão específico, mas o princípio SRP indica que essa classe deve ser dividida em duas, uma para leitura e outra para cálculos.

# Princípio do Aberto/Fechado (OCP)

Exemplo: Processamento de pagamentos com diferentes métodos de pagamento usando o padrão Strategy.

```php
interface MetodoPagamento {
    public function processarPagamento($valor);
}

class CartaoCredito implements MetodoPagamento {
    public function processarPagamento($valor) {
        // Processamento de pagamento via cartão de crédito
    }
}

class PayPal implements MetodoPagamento {
    public function processarPagamento($valor) {
        // Processamento de pagamento via PayPal
    }
}

class ProcessadorPagamento {
    private $metodoPagamento;

    public function setMetodoPagamento(MetodoPagamento $metodo) {
        $this->metodoPagamento = $metodo;
    }

    public function processar($valor) {
        $this->metodoPagamento->processarPagamento($valor);
    }
}
```

# Princípio da Substituição de Liskov (LSP)
Exemplo: Usando o princípio LSP com um padrão Template Method.

```php
abstract class Forma {
    abstract public function calcularArea();
}

class Circulo extends Forma {
    public function calcularArea() {
        // Cálculo da área do círculo
    }
}

class Retangulo extends Forma {
    public function calcularArea() {
        // Cálculo da área do retângulo
    }
}

function calcularAreaTotal(Forma $forma1, Forma $forma2) {
    return $forma1->calcularArea() + $forma2->calcularArea();
}
```

Padrão de Projeto Associado: Padrão Template Method para permitir que subclasses implementem detalhes específicos enquanto o fluxo geral é mantido na classe base.

# Princípio da Segregação de Interface (ISP)
Exemplo: Um exemplo simplificado de segregação de interfaces com um padrão Adapter.

```php
interface Trabalhador {
    public function trabalhar();
}

interface Comedor {
    public function comer();
}

class Empregado implements Trabalhador, Comedor {
    public function trabalhar() {
        // Implementação do trabalho
    }

    public function comer() {
        // Implementação da alimentação
    }
}

class Robo implements Trabalhador {
    public function trabalhar() {
        // Implementação do trabalho
    }
}
```

Padrão de Projeto Associado: Padrão Adapter para adaptar a interface do Robô para a interface Trabalhador.

# Princípio da Inversão de Dependência (DIP)
Exemplo: Usando o princípio DIP com Injeção de Dependência.

```php
class BancoDados {
    public function consultar($query) {
        // Consulta ao banco de dados
    }
}

class LogicaNegocio {
    private $bancoDados;

    public function __construct(BancoDados $bancoDados) {
        $this->bancoDados = $bancoDados;
    }

    public function processar() {
        // Utiliza o banco de dados
    }
}
```

Padrão de Projeto Associado: Injeção de Dependência para passar dependências para uma classe em vez de codificá-las diretamente.

## Contribuições

Contribuições, correções e sugestões são bem-vindas! Se você encontrar algum problema ou quiser adicionar mais exemplos, fique à vontade para abrir um pull request.
