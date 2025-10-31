# Separação dos materiais

A atividade tem como proposta o desenvolvimento de um sistema semelhante a um semáfaro, ou seja, três leds que piscam em looping a cada determinado período de tempo. Para isso, inicialmente é feita uma separação dos componentes utilizados:

- 1 Protoboard;

- 1 led vermelho;

- 1 led verde;

- 1 led amarelo;

- 1 arduíno uno;

- jumpers;

- 3 resistores de ... homs.

Com esses itens já é possível montar o sistema, garantindo o funcionamento da entrega.

# Montagem física

A próxima etapa consiste na montagem do sistema utilizando os componentes citados anteriormente. 

## Portas utilizadas

Para isso, os jumpers são conectados nas portas digitais do arduíno (para esse exercício serão utilizadas as portas 11, 12 e 13) e no GND. A seguinte imagem demonstra essa conexão:

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 43_e2d4a8f9](https://github.com/user-attachments/assets/234f204e-4cff-4b66-a650-07112fe37333)


## Energização da protoboard

Com as portas estabelecidas, o jumper conectado ao GND é ligado na coluna negativa da protoboard, pois essa entrada não irá variar de acordo com o led.

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 43_e101c74a](https://github.com/user-attachments/assets/285561cb-146c-4ecc-b0d6-fb127605a1eb)


Já as portas positivas (11, 12 e 13) são ligadas em linhas separadas, pois irão rotacionar o envio de energia, dessa forma, a organização mantém uma visualização simples, funcional e de fácil entendimento.

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 43_e101c74a](https://github.com/user-attachments/assets/285561cb-146c-4ecc-b0d6-fb127605a1eb)

Com isso feito, a protoboard já recebe energia adequadamente para o funcionamento do semáfaro.

## Ligação dos resistores

Após a energização da protoboard, os resistores são posicionados para receberem a energia enviada pelo arduíno. Para isso, ele deve ser posicionado antes do led, já que ele atua como um filtro para impedir que uma voltagem muito alta o queime. O mesmo processo deve ser feito para os 3 jumpers positivos.

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 43_af93d26c](https://github.com/user-attachments/assets/5beeaec5-f268-4eb6-ac3d-f307cfed6cd6)


## Leds

Com os resistores posicionados, a próxima etapa é a implantação dos leds, para isso, a perna maior, ou seja, a positiva deve ficar na mesma linha que a extremidade do resistor oposta a conexão dele, para que sua função seja exercida corretamente. Em seguida, a perna menor, ou negativa, do led deve ser conectada à coluna negativa por meio de um jumper.

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 44_6024fcad](https://github.com/user-attachments/assets/e05716e9-73e8-406c-93e5-4522bee88c15)


O mesmo processo deve ser realizado para os 3 leds, respeitando o espaçamento de cada jumper para garantir uma estrutura organizada.

## Circuito completo

Por fim, o sistema físico está completo e pronto para uso, já podendo ser conectado diretamente ao computador por meio do cabo de conexão do arduíno.

![Imagem do WhatsApp de 2025-10-31 à(s) 11 46 44_da911ee9](https://github.com/user-attachments/assets/ba7050c7-7010-4e96-a92d-881c931198db)


# Código

Com a montagem do circuito físico feita, o seguinte código é feito para garantir seu funcionamento:

```
class Semaforo {
private:
  int ledVermelho;
  int ledAmarelo;
  int ledVerde;
  int tempoVerde;
  int tempoAmarelo;
  int tempoVermelho;

public:
  Semaforo(int pVerde, int pAmarelo, int pVermelho, int tVerde, int tAmarelo, int tVermelho) {
    ledVerde = pVerde;
    ledAmarelo = pAmarelo;
    ledVermelho = pVermelho;
    tempoVerde = tVerde;
    tempoAmarelo = tAmarelo;
    tempoVermelho = tVermelho;

    pinMode(ledVerde, OUTPUT);
    pinMode(ledAmarelo, OUTPUT);
    pinMode(ledVermelho, OUTPUT);
  }

  void ligarVerde() {
    digitalWrite(ledVerde, HIGH);
    delay(tempoVerde);
    digitalWrite(ledVerde, LOW);
  }

  void ligarAmarelo() {
    digitalWrite(ledAmarelo, HIGH);
    delay(tempoAmarelo);
    digitalWrite(ledAmarelo, LOW);
  }

  void ligarVermelho() {
    digitalWrite(ledVermelho, HIGH);
    delay(tempoVermelho);
    digitalWrite(ledVermelho, LOW);
  }

  void ciclo() {
    ligarVerde();
    ligarAmarelo();
    ligarVermelho();
  }
};


Semaforo semaforo(11, 12, 13, 6000, 2000, 4000);

void setup() {
}

void loop() {
  semaforo.ciclo();
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

[vídeo](https://youtu.be/MdYzWa9HYTc)
