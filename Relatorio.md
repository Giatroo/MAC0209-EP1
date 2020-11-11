# Relatório sobre o EP1 de MAC0209 do ano de 2020

## Sobre os autores

O projeto foi desenvolvido pelo grupo de cinco alunos do terceiro período. Seguem seus nomes e número USP:

__Eduardo Brancher Urenha - 8587409__
__Leonardo Costa Santos - 10783142__
__Lourenço Henrique Moinheiro Martins Sborz Bogo - 11208005__
__Lucas Paiolla Forastiere - 11221911__
__Miguel de Mello Carpi - 11208502__

## Sobre as reuniões e decisões de projeto

Como, no periodo em que o projeto ocorreu, o Estado de São Paulo estava em quarentena, devido ao _Covid-19_, os experimentos, parte essencial do projeto, acabaram sendo comprometidos e eles foram substituídos por dados entregues pelos professores.

Dessa forma, o nosso cronograma acabou não abarcando os experimentos, mas apenas reuniões e os períodos de programação individual de cada membro (que não foram estipulados exatamente).

Nossa primeira reunião foi dia 15/04 e nela definimos o que cada um faria, definimos uma segunda reunião para o começo de Maio e uma para perto da entrega. 

Na reunião de 15/04 ficaram definidas as seguintes funções para cada membro do grupo:

__Eduardo Brancher Urenha__ - Pseudocódigo de todas as funções;
__Leonardo Costa Santos__ - Funções em Python de tudo;
__Lourenço Henrique Moinheiro Martins Sborz Bogo__ - Funções em Python de tudo;
__Lucas Paiolla Forastiere__ - Relatório;
__Miguel de Mello Carpi__ - Animação dos Movimentos.

Apesar dessas definições iniciais, as outras duas reuniões tinham o intuito de verificar se tudo estava sendo feito corretamente e se alguém precisava de ajuda com alguma coisa.

Na reunião do começo de Maio, nós ainda estávamos passando os pseudocódigos para Python, então usamos essa reunião para nos ajudar. Depois dela, os primeiros gráficos começaram a sair do papel.

Nós usamos a última reunião, próxima da entrega, para dar os últimos detalhes, finalizar o relatório e corrigir os possíveis bugs que restaram. 

## Sobre os dados e erros

Todos os dados podem ser encontrados nas tabelas contidas nos arquivos .csv. Vamos, portanto, discutir os erros que encontramos nos movimentos e ver se esses erros mudam de movimento para movimento e também se encontramos diferenças de erro entre os movimentos.

### Lançamento de Projétil

A primeira coisa que notamos é que não há erro nas acelerações, pois não estamos usando uma aproximação para elas.

Além disso, o erro na velocidade existe apenas em y, pois é nesse eixo que estamos estimando-a. No eixo x, ela é constante e, disso, o erro é nulo. Sobre esse erro na velocidade y, vemos que ele aumenta linearmente em cerca de 0,1.

Já na posição, temos erro nos dois eixos. Nós vemos que esse erro cresce, inicialmente, em cerca de 0,07 por passo, mas pouco depois, esse erro cresce para um acúmulo de 0,1 por passo.

A posição em y, entretanto, possui um erro muito menor. Além disso, esse erro passa a decrescer após o pico. Em todo o tempo, ele muda cerca de 0,08 de uma iteração para a outra.

### Movimento Uniformemente Variado

Novamente, vemos que o erro acontece somente da velocidade e posição. Mas dessa vez, o erro da velocidade está em x. Entretanto, o erro é ínfimo, em cerca de $10^{-14}$. Além disso, a variação do erro é bem estranha. Em alguns momentos ele fica constante, em outros ele aumenta, outro ele diminiu. Tem momento até que ele chega a zerar. Por fim, vemos que no fim ele se mantem na ordem de $10^{-13}$ e vai crescendo constantemente.

Já os erros nas posições são muito constantes. No eixo x, o erro é sempre 0,00015 aproximadamente. E no eixo y, o erro é sempre 0,0004 aproximadamente. Esses erros vão se acumulando conforme as iterações e lentamente teremos um erro grande e notável.

### Rampa 

Vemos agora que a aceleração continua sem erro, mas as duas velocidades e duas posições possuem erros. Entretanto, vemos algo interessante, os erros e x e em y são exatamente os mesmos.

Na velocidade, temos um erro maior que parece não ser linear (pode ser quadrático ou linear vezes logarítmico). Vemos que no começo o erro aumenta entre uma iteração e outra cerca de 0,07 e vai subindo para 0,20, 1 e no final a diferença entre os erros de duas iterações é de quase 10. 

Já na posição, vemos claramente que o erro é quadrático. Inicialmente, esse erro é menor do que o da velocidade, mas ao final, esse erro é incrivelmente maior (quase o dobro). Inicialmente, a variação do erro é menos que 0,001, mas ao final, essa variação é mais de 30.

### Movimento Circular

Por fim, vemos que a tabela do movimento circular está completemente zerada. Isso porque utilizamos a velocidade angular para os calculos e, então, o modo de calcular analiticamente e numericamente acaba sendo o mesmo.