# Form-validation
 Um exercício sobre Validando um Formulário em JavaScript puro usando classes.

Primeiramente eu tenho uma classe que faz a validação do formulário. O constructor() ele é responsável por chamar o formulário através da classe form e posteriormente ele faz a chamada do metódo events usando o this. O método events adiciona o evento submit que vai fazer o envio do formulário e o método handleSubmit receberá os dados do formulário se a validação do formulário for bem sucedida. A seguir temos os outros métodos: areValidPasswords() que verifica se as senhas são válidas, areValidCamps() verifica se os campos são válidos ele faz um loop for o primeiro percorre o formulário através da variável errorText e remove o erro, ou seja, se o erro já foi mostrado ou se o campo está correto ele remove as mensagens de erro, no segundo for ele seleciona a classe validar, a variável label retorna o nome de cada campo do formulário com erro de que o campo x não pode estar vazio e abaixo as condições verificam se o campo contém a classe cpf e usuario e se for diferente do método a validação passa a ser falsa.

O método ValidUser(camp) ele recebe uma propriedade chamada camp onde ele faz a validação do campo usuário se o usuário digitou o que foi pedido, então eu tenho a variável user ela recebe o valor do campo usuário, adiante eu tenho a variável valid que começa com valor true, ou seja, o campo do formulário é dado como válido de início significa que o usuário correspondeu aos requisitos, caso o valor seja false ele cria um erro na tela através do método createError(), e na segunda condição é feito a verificação dos caracteres utilizando uma expressão regular e fora da condição eu retorno a variável valid. 

O método validCPF(camp) chama a classe ValidCPF do arquivo validCpf.js onde ele vai criar um novo CPF e verifica se o CPF é válido. E por último, o método createError vai criar um paragráfo dizendo qual é o erro do campo. 

O arquivo validCpf é quem faz a validação do meu CPF, o método isSequencia verifica se o tamanho do CPF contém 11 números, o método geraNovoCpf() contém 3 variáveis onde a primeira variável vai pegar o CPF sem os 2 caracteres finais, o digito1 recebe o cpfSemDigitos para gerar o primeiro digito e a variável digito2 vai fazer a soma dos 9 caracteres + o primeiro digito gerado e no this.novoCPF eu estou gerando um novo CPF.

O método geraDigito() recebe a propriedade cpfSemDigitos contém a variável total que inicialmente começa com o valor 0, a variável reverso vai contar de trás para frente ele começa com o tamanho do CPF só que o tamanho dele é 9, então eu faço a soma do tamanho do CPF + 1 e na próxima vez que eu mandar o CPF com o digito ele vai vir com 10 caracteres e então o CpfSemDigitos vai passar a ser 11. O For vai somar o total com o reverso x a StringNumerica e aqui eu declaro ela como Number para garantir que a variável StringNumerica seja um número. Fora do Loop For eu faço 11 - o resto da divisão entre total e 11 e daí eu retorno se o digito for menor ou igual a 9 e ao contrário disso eu retorno 0 como uma string. 

Detalhe: Ele é um método estático pois em nenhum momento eu uso a palavra this isso significa que eu não preciso de nada da instância então quando eu não utilizo o this em um método significa que ele pode se tornar static. Então eu não funcionaria por exemplo eu fazer:

this.geraDigito()

Gera um erro porque this é a minha instância e métodos estáticos são métodos da classe. Para eu converter esse método para estático eu uso o nome da classe ValidCPF.

O método valid() faz o seguinte:

Se não existir a variável cpfLimpo return false;
Se o tipo de dado da variável cpfLimpo for diferente de string return false;
Se o tamanho de cpfLimpo for diferente de 11 caracteres return false;
Se é uma sequência de CPF, ou seja, se contém 11 caracteres se não houver return false;
Gera um novo CPF;
Retorna se o CPF novo é igual ao CPF que me foi enviado;
