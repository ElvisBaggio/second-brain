Os 0,02 que são abaixo de 85%, vcs tem visão do quanto tem de falso positivo? Será que não vale estudar antes de mudar? 1319 casos é bastante, não?

Quando subimos a mudança de BH? Como ficaram os demais dados/resultados?
		Queria ver se mudamos a curva de desativações e contestações
		- Dados de aprovação
		- Report dos clientes e parceiros
		- etc..


Ciro, não são drivers únicos, aqui são requisições.  Hoje 44% dos drivers tem mais de 1 requisição e temos casos de drivers com mais de 100.

Separando um pouco as ações:

**Mudança na esteira de biometria temos esses resultados:**
Geral
Match - 98,16%
Not Match - 0,64%
Phone Found - 0,61%

Olhando para o recorte do teste Foto de Cadastro
Match - 96,23%
Not Match - 1,41%
Phone Found - 1%

**Novo modelo de not match e phone found**

Na semana passada nós desligamos dois modelos (not match e phone found) e subimos um novo modelo que valida esses dois cenários. 
Isso muda a forma como desativamos os drivers. Antes eram casos consecutivos e agora é por séries temporal.

Estamos conseguindo mapear os falso positivos, dado que só estamos desativando após a validação pelo time de qualidade por um output do modelo nessa planilha.
https://docs.google.com/spreadsheets/d/1qv38b7PmlUTeCiEYqr7Rxl2295a4qJ0r0f_gihYADBk/edit#gid=1209778766

Resultados desse combo modelo + validação (modelo ligado desde o dia 28/08)
299 -> 958 drivers desativados 
67 (29%) -> 17 (1,8%) reativações


**Como isso converge com a alteração de threshold**
Em tese devemos ter mais not_matches, e caso eles caiam no modelo, vão passar por esse processo de validação

Não dá para ter esse processo rodando para sempre, precisamos melhorar a assertividade do modelo. 

Fiquei em dúvida quando você fala sobre Dados de aprovação, o que seria?

#produto #trabalho #facematch