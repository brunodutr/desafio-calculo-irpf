# Desafio Cálculo Imposto de Renda (Mensal)

## Objetivo

Realizar o cálculo do imposto de renda mensal a ser descontado a partir do salário informado e número de dependentes.

O resultado deve possuir as seguintes informações:

1. Imposto INSS
2. Imposto IRPF
3. Desconto total
4. Salário com descontos

## Detalhamento Funcionalidade

O cálculo do imposto de renda mensal é realizado a partir dos seguintes passos:

1. Calcular o valor devido de INSS
   - Encontrar a Regra de cálculo na [Tabela 1](#tabela-1---inss-2019) a partir do **Salário**
   - Multiplicar o Salário pela **Alíquota**, observando o limite máximo de desconto (*impostoINSS*)
   - Subtrair o '*impostoINSS*' do **Salário**
2. Calcular o valor devido de IRPF
   - Calcular o desconto total de dependentes (*descontoDependentes*)
   - Subtrair o '*descontoDependentes*' do **Salário**
   - Encontrar a Regra de cálculo na [Tabela 2](#tabela-2---irpf-2019) a partir do **Salário**
   - Multiplicar o **Salário** pela **Alíquota** (*impostoIRPF*)
   - Subtrair **Desconto** de '*impostoIRPF*'
   - Subtrair o '*impostoIRPF*' do **Salário**

**Todo cálculo deve ter precisão na segunda casa decimal e arredondamento para cima*

#### Tabela 1 - INSS 2019

| Salário (R$)	             | Alíquota (%) |
| :------------------------: | :----------: | 
| Até 1.751,81	             | 8,00%        |
| De 1.751,82 até 2.919,72	 | 9,00%        | 
| De 2.919,73 até 5.839,45*  | 11,00%       |

**O valor máximo do INSS é R$ 642,34*

#### Tabela 2 - IRPF 2019*

| Salário (R$)	            | Alíquota (%)	|  Desconto (R$)                  | 
| :-----------------------: | :-----------: | :-----------------------------: | 
| Até 1.903,98	            | 0%     	      | R$ 0,00                         | 
| De 1.903,99 até 2.826,65  | 7,5%	        | R$ 142,80                       | 
| De 2.826,66 até 3.751,05  | 15%	          | R$ 354,80                       | 
| De 3.751,06 até 4.664,68  | 22,5%	        | R$ 636,13                       | 
| Acima de 4.664,68	        | 27,5%	        | R$ 869,36                       | 

**Sendo o valor de desconto mensal para cada dependente de R$189,59*

## Detalhamento Técnico

É necessário que o sistema possua uma Interface*, que receba os parâmetros:
  - Salário
  - Número de dependentes
  
**A interface pode ser Console, Web ou API (mais simples possível sendo necessária apenas para interação com o sistema)*

### Tecnologias Obrigatórias

  - Java (versão 8 ou superior)
  - Junit (versão 4.12 ou superior)
  - Maven (versão 3.6.1 ou superior)

## Exemplos

#### Exemplo 1

```console

Paramêtros:
  salario = 1000.00
  numero_dependentes = 0

Resultado:
  imposto_inss = R$ 80.00
  imposto_irpf = R$ 0,00
  desconto_total = R$ 80.00
  salario_final = R$ 920.00
  
```

#### Exemplo 2

```console

Paramêtros:
  salario = R$ 3000.00
  numero_dependentes = 2

Resultado:
  imposto_inss =  R$ 330.00
  imposto_irpf = R$ 29.01
  desconto_total = R$ 359.01
  salario_final = R$ 2640.99
  
```

#### Exemplo 3

```console

Paramêtros:
  salario = 6000.00
  numero_dependentes = 0

Resultado:
  imposto_inss = R$ 642.34
  imposto_irpf = R$ 604.00
  desconto_total = R$ 1246.34
  salario_final = R$ 4753.66
  
```

## Desenvolvimento

Recomendamos que você utilize seu repositório pessoal para organizar suas atividades de desenvolvimento. 
Trabalhe com commits organizados e envie pequenas alterações para sua branch sempre que tiver o código e aplicação estáveis para execução.

Assim que finalizado seu projeto, enviar link do seu github com o desafio.

## Avaliação

Você será avaliado nos seguintes aspectos, em ordem de prioridade:
1. Correta execução da especificação funcional;
2. Legibilidade de código;
3. Modelagem e OO (Orientação à Objetos);
4. Uso apropriado do Java, assim como os frameworks e suas melhores práticas;
5. Testes Unitários (Opcional);



É esperado que você desenvolva sem ajuda ou intervenção direta de terceiros, mas encorajamos que você pesquise por soluções e boas práticas sem nenhum tipo de restrição, apenas lembre-se que, caso seja aprovado para a próxima etapa, serão realizadas perguntas na entrevista, a fim de certificar seu conhecimento total sobre a implementação. 

**Jogue limpo!**
