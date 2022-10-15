## Sistemas Distribuidos - RMI

### João Pedro de Alcântara Lima | Engenharia da Computação

##

### Java RMI 

É um mecanismo para permitir a invocação de métodos que residem em diferentes máquinas virtuais Java (JVM). 
O JVM pode estar em diferentes máquinas ou podem estar na mesma máquina. Em ambos os casos, o método pode ser executado em um endereço diferente do processo de chamada. 
Java RMI é um mecanismo de chamada de procedimento remoto orientada a objetos.

### Aplicação de objetos distribuídos
Uma aplicação RMI é frequentemente composto por dois programas diferentes, um servidor e um cliente. O servidor cria objetos remotos e faz referências a esses objetos disponíveis. Em seguida, ele é válido para clientes invocarem seus métodos sobre os objetos.

O cliente executa referências remotas aos objetos remotos no servidor e invoca métodos nesses objetos remotos.

O modelo de RMI fornece uma aplicação de objetos distribuídos para o programador. Ele é um mecanismo de comunicação entre o servidor e o cliente para se comunicarem e transmitirem informações entre si. A aplicação de objetos distribuídos tem de prover as seguintes propriedades:

<ul>
  <li>Localização de objetos remotos: O sistema tem de obter referências a objetos remotos. Isto pode ser feito de duas maneiras. Ou, usando as instalações de nomeação do RMI, o registro RMI, ou passando e retornando objetos remotos.</li>
  <li>Comunicação com objetos remotos: O desenvolvedor não tem de lidar com a comunicação entre os objetos remotos desde que este é tratado pelo sistema RMI.</li>
  <li>Carregar os bytecodes de classe dos objetos que são transferidos como argumentos ou valores.</li>
</ul>

Todos os mecanismos para carregar o código de um objeto e transmitissão dos dados são fornecidos pela RMI system.40

### Interfaces e Classes
Java RMI é um sistema de linguagem individual, a programação de aplicação distribuída em RMI é bastante simples. Todas as interfaces e classes para o sistema de RMI são definidos no pacote java.rmi. A classe de objeto remoto implementa a interface remota, enquanto as outras classes estendem RemoteObject.

### A interface remota
Uma interface remota é definida pela extensão da interface Remote que está no pacote java.rmi. A interface que declara os métodos que os clientes podem invocar a partir de uma máquina virtual remoto é conhecido como interface remota. A interface remota deve satisfazer as seguintes condições:

<ul>
  <li>Deve estender-se a interface Remote.</li>
  <li>Cada declaração de método na interface remota deve incluir a exceção RemoteException (ou uma de suas superclasses), em sua cláusula lançada.</li>
</ul>

### A classe RemoteObject
Funções do servidor RMI são fornecidos pela classe RemoteObject e suas subclasses Remote Server, Activatable e UnicastRemoteObject. Aqui está uma breve descrição de como lidar com as diferentes classes:

RemoteObject fornece implementações dos métodos toString, equals e hashCode na classe java.lang.Object.
As classes UnicastRemoteObject e Activatable cria objetos remotos e os exporta, ou seja, essas classes fazem os objetos remotos usados por clientes remotos.

### A classe RemoteException
A classe RemoteException é uma super-classe das exceções que o sistema RMI joga durante uma invocação de método remoto. Cada método remoto que é declarado em uma interface remota deve especificar RemoteException (ou uma de suas superclasses), em sua cláusula throws para garantir a robustez das aplicações no sistema RMI.

Quando uma chamada de método remoto tiver um erro, a exceção RemoteException é lançada. Falha de comunicação, erros de protocolo e falha durante a triagem ou unmarshalling de parâmetros ou valores de retorno são algumas das razões para o fracasso da comunicação RMI. RemoteException é uma exceção que deve ser tratada pelo método chamador. O compilador confirma que o programador de ter lidado com essas exceções.
