# Separação dos materiais

A atividade tem como proposta o desenvolvimento de um sistema semelhante a um semáfaro, ou seja, três leds que piscam em looping a cada determinado período de tempo. Para isso, inicialmente é feita uma separação dos componentes utilizados:

- 1 Protoboard;

- 1 led vermelho;

- 1 led verde;

- 1 led amarelo;

- 1 arduíno uno;

- jumpers;

- 3 resistores de ... homs.

imagem

Com esses itens já é possível montar o sistema, garantindo o funcionamento da entrega.

# Montagem física

A próxima etapa consiste na montagem do sistema utilizando os componentes citados anteriormente. 

## Portas utilizadas

Para isso, os jumpers são conectados nas portas digitais do arduíno (para esse exercício serão utilizadas as portas 11, 12 e 13) e no GND. A seguinte imagem demonstra essa conexão:

imagem

## Energização da protoboard

Com as portas estabelecidas, o jumper conectado ao GND é ligado na coluna negativa da protoboard, pois essa entrada não irá variar de acordo com o led.

imagem

Já as portas positivas (11, 12 e 13) são ligadas em linhas separadas, pois irão rotacionar o envio de energia, dessa forma, a organização mantém uma visualização simples, funcional e de fácil entendimento.

imagem

Com isso feito, a protoboard já recebe energia adequadamente para o funcionamento do semáfaro.

## Ligação dos resistores

Após a energização da protoboard, os resistores são posicionados para receberem a energia enviada pelo arduíno. Para isso, ele deve ser posicionado antes do led, já que ele atua como um filtro para impedir que uma voltagem muito alta o queime. O mesmo processo deve ser feito para os 3 jumpers positivos.

imagem

## Leds

Com os resistores posicionados, a próxima etapa é a implantação dos leds, para isso, a perna maior, ou seja, a positiva deve ficar na mesma linha que a extremidade do resistor oposta a conexão dele, para que sua função seja exercida corretamente. Em seguida, a perna menor, ou negativa, do led deve ser conectada à coluna negativa por meio de um jumper.

imagem

O mesmo processo deve ser realizado para os 3 leds, respeitando o espaçamento de cada jumper para garantir uma estrutura organizada.

## Circuito completo

Por fim, o sistema físico está completo e pronto para uso, já podendo ser conectado diretamente ao computador por meio do cabo de conexão do arduíno.

imagem

# Código

Com a montagem do circuito físico feita, o seguinte código é feito para garantir seu funcionamento:

```
int led_vermelho = 13;
int led_amarelo = 12;
int led_verde = 11;

void setup() {
  pinMode(led_vermelho, OUTPUT);
  pinMode(led_amarelo, OUTPUT);
  pinMode(led_verde, OUTPUT);
}

void loop() {
  digitalWrite(led_verde, HIGH);
  delay(4000); 
  digitalWrite(led_verde, LOW);

  digitalWrite(led_amarelo, HIGH);
  delay(2000);
  digitalWrite(led_amarelo, LOW);

  digitalWrite(led_vermelho, HIGH);
  delay(6000);
  digitalWrite(led_vermelho, LOW);
}
```

O código se inicia com a definição das portas de cada led, então:

- led vermelho: porta 13;

- led amarelo: porta 12;

- led verde: porta 11.

Após isso o void setup define as portas dos leds como outputs, ou seja, elas irão enviar energia para o circuito.

E por fim, o void loop define o intervalo de tempo em que cada led fica aceso, sendo o led verde 4 segundos, o amarelo 2 e o vermelho 6. 

O led verde é definido primeiro para o semáfaro iniciar dessa cor, em seguida ele segue a mesma ordem contida no código. Após isso, o código está completamente funcional e o sistema já está pronto para uso.

# Vídeo de demonstração

As etapas anteriores descreveram como o circuito deve ser montado, e, após isso, deve ser obtido um semáfaro totalmente funcional. Para demonstrá-lo, segue um vídeo que exibe seu funcionamento de forma clara:

vídeo
