# Desafio Processamento de Dados Simplificado com Power BI 📊
Transformação de dados utilizando o Power BI. A realização deste projeto faz parte das tarefas do curso Python Data Analytics.

### Tecnologia Utilizada
- Power BI.

### Créditos
Este código foi desenvolvido como parte das tarefas do curso da DIO - Python Data Analytics. 
Os dados utilizados são fornecidos pela instrutora Juliana Mascarenhas (https://github.com/julianazanelatto)

### Base de dados utilizada no desafio
https://github.com/julianazanelatto/power_bi_analyst/tree/b010c1874a183a0fb4b831e76dc68b9b872becec/M%C3%B3dulo%203/Desafio%20de%20Projeto

**Observação importante**: Não foi utilizado nem o MySQL, nem o Azure para integrar o banco de dados ao Power BI. Ao invés disso, foram importados dados de uma planilha de Excel. Para realizar a transformação de sql em csv, foi utilizada uma ferramenta online de conversão (por livre escolha, não foi utilizado o MySQL para fazer a conversão):
https://bfotool.com/sql-to-csv

### Desafio
- **Objetivo**: Transformar os dados fornecidos verificando a coerência dos tipos de dados, mesclar informações, corrigir valores nulos, remover dados não necessários para a análise, separar colunas complexas, e os demais processos necessários para transformar os dados.

### Passos realizados para a conclusão do desafio
-> Modificação do tipo de dado na tabela employee, coluna salary.

-> Correção do dado de horas - não reconheceu corretamente ao importar.

-> Modificação do tipo de dados na tabela works_on, coluna hours.

-> Identificação do James como gerente:  Super_ssn com valor nulo que foi preenchido com o valor de 888665555

   Identificação dos gerentes de cada departamento verificando os valores iguais de Ssn(Tabela Employee) e Mgr_ssn(Tabela departament) 
   
	    - Franklin- Research (333445555)
	    - Jennifer- Administration (987654321)
	    - James - Headquarter (888665555)
     
-> Divisão da coluna de endereços (separação de colunas complexas).

-> Tarefa: mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores e explicar a diferença entre mesclar e atribuir.

Ao mesclar eu escolhi qual seria a referência de junção, o que tem de similar em ambas as tabelas, neste caso, utilizei o número do departamento. Assim, ele criou uma nova tabela com todas as informações correspondentes, juntando as duas tabelas. Os dados que não tinham correspondência, foram eliminados.
![image](https://github.com/profa-janaina/Desafio-Processamento-de-Dados-Simplificado-com-Power-BI/assets/111704392/8e412c67-5a55-4a3d-8503-788c324be9ce)

Ao acrescentar, ele tentou juntar os dados de acordo com as correspondências entre as duas tabelas. Contudo, ele também adicionou os dados que não tem correspodência e completou com nulo os dados sem correspondência. Ou seja, ele fez a combinação do que tinha correspondência e completou a tabela com os dados resultantes, preenchendo com nulo só para completar a tabela onde os dados não tinham correspondência.
![image](https://github.com/profa-janaina/Desafio-Processamento-de-Dados-Simplificado-com-Power-BI/assets/111704392/b992eb0c-f9f4-467d-bd39-2b80db7e4d58)

Isso ficou bem claro quando analisei a quantidade de colunas e linhas.

    - Mesclar -> 18 colunas, 8 linhas
    - Atribuir -> 23 colunas, 11 linhas 

A tabela employee possui 13 colunas e 8 linhas. A tabela departament possui 5 colunas e 3 linhas. Isso demonstra claramente que o atribuir exibi todos os dados, enquanto o mesclar só os correspondentes de acordo com o critério de junção.

-> Agrupamento das colunas firstName e LastName para gerar o nome completo do colaborador.

-> Agrupamento de colaboradores por gerente (Para isso, foi utilizado o comando text.combine para agrupar textos e '#(cr)" para colocar os nomes dos colaborades em cada linha)

-> Agrupamento dos departamentos por localização.

-> Remoção de colunas e tabelas desnecessárias:
  
    - Tabela                Colunas
 	   departament              Mgr_start_date // Dept_create_date
	   dependent                todas as colunas (não foi utilizada)
	   employee                 Minit // Bdate // Address(number, street, city, state) // Sex // Salary 
	   project                  Todas as colunas (não foi utilizada)

Deixe uma ⭐️ se você gostou do projeto!
