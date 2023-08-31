# O que são Design Patters? 

são soluções reutilizáveis para problemas comuns de design de software. Eles representam abordagens testadas e comprovadas para projetar e estruturar código de maneira eficaz, tornando-o mais flexível, manutenível e compreensível. Padrões de projeto não são códigos concretos, mas sim descrições genéricas de como resolver determinados problemas em uma variedade de contextos.

## Geralmente, os padrões de projeto são divididos em três categorias principais:

**Padrões de Criação:** Esses padrões estão relacionados à criação de objetos. Eles ajudam a abstrair o processo de criação, tornando-o mais flexível e adaptável.

**Padrões Estruturais:** Esses padrões tratam da composição de classes e objetos para formar estruturas maiores. Eles ajudam a organizar as classes de maneira mais eficiente e clara.

**Padrões Comportamentais:** Esses padrões estão focados nos comportamentos e interações entre objetos. Eles lidam com a comunicação e responsabilidades entre objetos.

Os padrões de projeto fornecem várias vantagens:

**Reutilização de Soluções:** Ao seguir padrões, você pode aproveitar soluções já criadas e testadas para problemas recorrentes.

**Comunicação Eficiente:** Os padrões são amplamente reconhecidos e compreendidos, facilitando a comunicação entre desenvolvedores.

**Manutenção Facilitada:** O código organizado por padrões é mais claro e estruturado, facilitando a manutenção e as futuras modificações.

**Flexibilidade:** Os padrões tornam o código mais flexível, permitindo que você introduza alterações ou expansões com menos impacto em outras partes do sistema.

No entanto, é importante notar que os padrões de projeto não são uma solução para todos os problemas. Eles devem ser usados quando apropriado e quando se alinham com as necessidades do projeto. Às vezes, a aplicação incorreta de padrões pode levar a código complexo e desnecessário.

## Exemplos:

1. Factory Method
O padrão Factory Method define uma interface para criar objetos em uma superclasse, mas permite que as subclasses escolham qual classe concreta instanciar.

```php
interface Criador {
    public function criarProduto();
}

class CriadorConcretoA implements Criador {
    public function criarProduto() {
        return new ProdutoA();
    }
}

class CriadorConcretoB implements Criador {
    public function criarProduto() {
        return new ProdutoB();
    }
}
```

2. Abstract Factory
O padrão Abstract Factory fornece uma interface para criar famílias de objetos relacionados sem especificar suas classes concretas.

```php
interface Fabrica {
    public function criarProdutoA();
    public function criarProdutoB();
}

class FabricaConcretaA implements Fabrica {
    public function criarProdutoA() {
        return new ProdutoA();
    }
    
    public function criarProdutoB() {
        return new ProdutoB();
    }
}
```

3. Singleton
O padrão Singleton garante que uma classe tenha apenas uma instância e fornece um ponto global para acessá-la.

```php
class Singleton {
    private static $instancia;

    private function __construct() { }

    public static function obterInstancia() {
        if (!self::$instancia) {
            self::$instancia = new self();
        }
        return self::$instancia;
    }
}
```

## Padrões Estruturais

1. Adapter
O padrão Adapter permite que objetos com interfaces incompatíveis trabalhem juntos através de um adaptador que converte a interface de um objeto em outra.

```php
interface Motor {
    public function ligar();
}

class MotorEletrico {
    public function ligar() {
        echo "Motor elétrico ligado." . PHP_EOL;
    }
}

class AdaptadorMotor implements Motor {
    private $motorEletrico;

    public function __construct(MotorEletrico $motorEletrico) {
        $this->motorEletrico = $motorEletrico;
    }

    public function ligar() {
        $this->motorEletrico->ligar();
    }
}
```

2. Decorator
O padrão Decorator permite adicionar comportamentos a objetos individualmente, de forma dinâmica, sem afetar outros objetos da mesma classe.
```php

interface Componente {
    public function operacao();
}

class ComponenteConcreto implements Componente {
    public function operacao() {
        echo "Operação do componente concreto." . PHP_EOL;
    }
}

class Decorador implements Componente {
    protected $componente;

    public function __construct(Componente $componente) {
        $this->componente = $componente;
    }

    public function operacao() {
        $this->componente->operacao();
    }
}

class DecoradorA extends Decorador {
    public function operacao() {
        parent::operacao();
        echo "Operação do decorador A." . PHP_EOL;
    }
}
```

## Padrões Comportamentais

1. Strategy
O padrão Strategy define uma família de algoritmos, encapsula cada um deles e os torna intercambiáveis. Isso permite que o algoritmo varie independentemente dos clientes que o utilizam.

```php
interface Estrategia {
    public function executar();
}

class EstrategiaA implements Estrategia {
    public function executar() {
        echo "Executando estratégia A." . PHP_EOL;
    }
}

class EstrategiaB implements Estrategia {
    public function executar() {
        echo "Executando estratégia B." . PHP_EOL;
    }
}

class Contexto {
    private $estrategia;

    public function setEstrategia(Estrategia $estrategia) {
        $this->estrategia = $estrategia;
    }

    public function executarEstrategia() {
        $this->estrategia->executar();
    }
}
```

2. Observer
O padrão Observer define uma dependência entre objetos de modo que quando um objeto muda de estado, todos seus dependentes são notificados e atualizados automaticamente.

```php
interface Observador {
    public function atualizar(string $mensagem);
}

class ObservadorConcreto implements Observador {
    private $nome;

    public function __construct(string $nome) {
        $this->nome = $nome;
    }

    public function atualizar(string $mensagem) {
        echo "Observador $this->nome recebeu a mensagem: $mensagem" . PHP_EOL;
    }
}

class Assunto {
    private $observadores = [];

    public function adicionarObservador(Observador $observador) {
        $this->observadores[] = $observador;
    }

    public function notificarObservadores(string $mensagem) {
        foreach ($this->observadores as $observador) {
            $observador->atualizar($mensagem);
        }
    }
}
```
