- Criado no Order
- Depois Criado no Bank

- Descontos etc, ficam no bank
	- Para poder devolver esses dados no order, precisamos ajustar no Payments\
	- O endpoint de post precisa devolver a lista de pedidos criados

- Ontem ia subir mas estava com problema no email aws. Assim que ajustar a gente ja sober
- Integração com WPP vai na sequencia




# Cancelamento de Pedidos

- Endpoint sera criado no Yaki,. Definições de regra ja temos
- App vai cancelar?

Regras: 1 - Regra de Cancelamento (Boleto)
Se meio de pagamento = Boleto
E status = Não Iniciado
E não tem NF cadastrada
E não tem pagamento ao fornecedor cadastrado -> pode cancelar

2 - Regra de Cancelamento (PIX)
Se meio de pagamento = PIX
E status = Aguardando Pagamento
E ANY parcela <> Pago
E não tem pagamento ao fornecedor cadastrado -> pode cancelar

3 - Regra de Cancelamento (Cartão)
Não dá para fazer agora


# Demandas do Antonio

Rotas:
- Ajustes de tags via script
- Thais e Clariamna acionando diretamente o Antonio pra fazer atividades que concorrem com o Bakcklog do time


#Cayena