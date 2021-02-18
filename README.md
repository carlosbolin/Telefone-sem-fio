Este  um projeto baseado em Pure Data e MobMuPlat para a peça Telefone Sem Fio da Orchidea (Orquestra de Ideias) do laboratório [ALICE](https://alice.dcomp.ufsj.edu.br/) da UFSJ.

Esta peça conta com o uso de 6 celulares dispostos em amplificadores cerâmicos e um computador que atua como o maestro desta orquestra.

# Sobre o projeto
- /examples: Esta pasta contém patches de PD (.pd) e arquivos do MobMuPlat (.mmp) que foram criados no decorrer do peça e que podem servir para aprender a utilizar estas tecnologias. Estes exemplos auxiliaram a criar as vozes desta peça, aqui chamadas de fofoqueiros.
- /sequences: Esta pasta contém exemplos de trechos de peças feitos como exemplo de partitura. Estes arquivos podem ser lidos pelo maestro da peça, aqui chamado de cidadão.


# Mensagens que o fofoqueiro conhece

O fofoqueiro conhece as seguintes mensagens:

* Apagar e acender o flash (lanterna)
```
/voice 0 /flash 0
/voice 0 /flash 1
```

* Ligar e desligar o vibrador
```
/voice 0 /vibrate 0
/voice 0 /vibrate 1
```

* Mudar a cor da tela
```
/voice 0 /canvas paintrect x1 y1 x2 y2 R G B A

Este parâmetros são: left x1, top y1, right x2, bottom y2, red R, green G, blue B, alpha A
```

* Criar ruído / parar ruído
```
/noise 1
/noise 0
```

* Tocar / parar oscilador (440hz)
```
/tuuu 1
/tuuu 0
```

* Manipular primeiro buffer de áudio
```
/grava 1
/grava 0
/tocasample

/tocaemloop
/paraoloop

/efeito

/tamanhosample
/velocidadesample

/iniciosample
```

* Manipular segundo buffer de áudio
```
/grava2 1
/grava2 0
/tocasample2
```

* Manipular terceiro buffer de áudio
```
/grava3 1
/grava3 0
/tocasample3
```

# Formato das sequências

O arquivo com as mensagens contém 3 campos principais: O tempo de duração daquela ação, a voz destino da ação e a ação em si.
Assim, no exemplo abaixo temos que as vozes 1, 2, 3 e 4 irão acender suas lanternas, e depois de 1 segundo (1000 milisegundos), irão apagar as mesmas.

```
0 /voice 0 /flash 1
0 /voice 1 /flash 1
0 /voice 2 /flash 1
0 /voice 3 /flash 1
1000 /voice 4 /flash 1
0 /voice 0 /flash 0
0 /voice 1 /flash 0
0 /voice 2 /flash 0
0 /voice 3 /flash 0
0 /voice 4 /flash 0
```

