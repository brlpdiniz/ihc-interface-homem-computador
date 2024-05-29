### *;1: consultar uma referência.​
```
*;1. consultar uma referência // números indicam a estrutura das metas (1, 1.1, 1.2, 2, etc.)​
*;1.1a: se (conhecer dados precisos sobre a referência) // letras indicam regras de seleção​
            então (realizar busca) //reuso​
                {   1: iniciar busca // métodos são representados entre chaves​
                    2: digitar dados conhecidos​
                    3: disparar busca​
                    4: verificar dados apresentados​
                    5: encerrar consulta }​

*;1.1b: se (não conhecer dados precisos sobre a referência)​
            então (realizar varredura) //reuso​
                  { 1: iniciar varredura​
                    2: comparar referência apresentada com a referência desejada​
                    3a: se (referência apresentada não for a desejada e houver próxima referência)​
                            então ({ 3a.1: ir para a próxima referência​
                                     2: comparar referência apresentada com a referência desejada }) // repetição e reuso
                    3b: se (referência apresentada for a desejada ou estiver na última referência)​
                            então (encerrar varredura)​
                    }
```

### FU1, FU2; 2: reservar um exemplar
```
FU1,FU2; 2. reservar um exemplar
se (conhecer dados precisos sobre o exemplar)
    então (realizar busca) //reuso​
    {
        1: iniciar busca
        2: digitar dados conhecidos​
        3: disparar busca​
        4: verificar dados apresentados​
        5: comparar exemplar apresentado com a exemplar desejado
        se (busca encontrada for desejada)
        
        5: selecionar exemplar
        6: reserva exemplar
    }

se (não conhecer dados precisos sobre o exemplar)​
    então (realizar varredura) //reuso​
    {
        1: iniciar varredura​
        2: comparar exemplar apresentado com a exemplar desejado
        3a: se (exemplar apresentado não for o desejado e houver próximo exemplar)​
            então ({ 3a.1: ir para o próximo exemplar​
                        2: comparar exemplar apresentado com a exemplar desejado }) // repetição e reuso
        3b: se (exemplar apresentado for o desejado ou estiver no último exemplar)​
            então (encerrar varredura)​
    }​
```