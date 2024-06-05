# (IHC) Interface Homem Computador - Modelagem de Tarefas
<br>

### Profº: Patricia Rucker de Bassi


| GRR | NOME |
| ------ | ------ |
| 2017208552 | Bruno Leandro Diniz |


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
                                     3a.2: comparar referência apresentada com a referência desejada }) // repetição e reuso
                    3b: se (referência apresentada for a desejada ou estiver na última referência)​
                            então (encerrar varredura)​ }
```

### FU1, FU2; 2: reservar um exemplar
```
FU1,FU2; 2. reservar um exemplar
2.1a: se (conhecer o exemplar específico)
    então (realizar reserva)
        {   1: iniciar reserva
            2: digitar dados do exemplar
            3: verificar disponibilidade
            4a: se (exemplar disponível)
                então ({  4a.1: confirmar reserva
                          4a.2: encerrar reserva })
            4b: se (exemplar não disponível)
                então (notificar indisponibilidade)
            5: encerrar processo de reserva }

FU1, FU2; 2.1b: se (não conhecer o exemplar específico)
    então (buscar exemplar)
        {   1: iniciar busca
            2: buscar por categoria ou autor
            3: comparar exemplares apresentados
            4a: se (exemplar desejado encontrado)
                então ({    4a.1: selecionar exemplar
                            4a.2: confirmar reserva
                            4a.3: encerrar reserva })
            4b: se (exemplar desejado não encontrado)
                então (notificar usuário)
            5: encerrar busca }
```

<div style="page-break-after: always;"></div>

### FU2; 3: registrar um empréstimo
```
FU2; 3: registrar um empréstimo
3.1a: se (livro estiver disponível)
    então (iniciar processo de empréstimo)
        {   1: digitar dados do usuário
            2: digitar dados do exemplar
            3: verificar disponibilidade do exemplar
            4a: se (exemplar disponível)
                    então ({ 4a.1: confirmar empréstimo
                               4a.2: registrar data de devolução
                               4a.3: finalizar processo de empréstimo })
            4b: se (exemplar não disponível)
                    então (notificar indisponibilidade e encerrar processo)
            }
```

### FU2; 5: registrar uma devolução
```
FU2; 5. registrar uma devolução
FU2; 5.1: iniciar processo de devolução
FU2; 5.2: digitar dados do exemplar
FU2; 5.3: verificar estado do exemplar
5.5a: se (exemplar em bom estado)
    então ({ 5.5a.1: registrar devolução
             5.5a.2: atualizar disponibilidade
             5.5a.3: finalizar processo de devolução })
5.5b: se (exemplar danificado)
    então (registrar dano e notificar usuário)
FU2; 5.5: encerrar processo de devolução
```