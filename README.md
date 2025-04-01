Análise e projeto de sistemas - projeto 4 - Modelagem de um pequeno sistema com UML e BPMN

Alunos: Anna Beatryz Gomes Gurgel e Antônio Alisson Teixeira Cruz Sala: 2-ds

Escola: Escola Estadual de Educação Profissional Deputado Roberto Mesquita
Professor: Everson


BPMN do sistema de reserva de sala:

[inicio] -> [receber pedido de cadastro] -> [verificar disponibilidade] -> {sala disponível?}<br>
                                                    -> [sim]<br>
                                                        -> [fazer a reserva da sala, para o usuário]<br>
                                                    -> [não]<br>
                                                        -> [informar o cliente que não será possível a reserva]<br>


UML do sistema de reserva de salas:


+----------------------------+<br>
         CLIENTE<br>
+----------------------------+<br>                 
  . id: int<br>
  . nome: string<br>
  . email: string<br>
+----------------------------+<br>
  . realizarPedidoDeReserva()    
+----------------------------+


+-----------------------------+<br>
 RESERVA<br>
+-----------------------------+<br>
 . id: int<br>
 . dataHora: dateTime<br>
 . status: string<br>
 . duração: int<br>
+-----------------------------+<br>
   . verificarDisponibilidade()<br>
   . confirmarPedido()<br>
   . informarCliente()<br>
+-----------------------------+<br>

 
+----------------------+<br>
SALA<br>
+----------------------+<br>
. id: int <br>
. nome:string <br>
. capacidade <br>
+----------------------+
<br>
<br>

cliente 1 ------ 0 reservas
  - Um CLIENTE pode ter várias RESERVAS.
  - Várias RESERVAS podem pertencer a um único CLIENTE

 reserva 0 ------ 1 sala
 - Várias RESERVAS equivalem a apenas uma SALA.
 - Uma SALA pode ter várias RESERVAS

