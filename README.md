
# ShowTheAtomDataManipulation
![linguagem](https://img.shields.io/badge/Python-2.7-brightgreen.svg)
![versão](https://img.shields.io/badge/version-v0.2-orange.svg)
Script for Manipulation of Data of Project Show The Atom

O que é o Projeto **Show The Atom**? É uma construção de um **software** disponível para **todas as plataformas** que **auxilia estudantes** com a **tabela periódica**, traz a mostra de maneira **rápida e prática** várias **informações sobre um átomo** que deseja saber mais.

- **Server**:
	Nosso server  para manipulação de dados foi feito com **NodeJS**, juntamento com o banco de dados **MariaDB** como podemos olhar no github do server: [ShowTheAtomServer](https://github.com/ProfessorJamesBach/ShowTheAtomServer)
 - **Situação atual**:
	 ````
	 def sitAtual():
	     r = requests.get('http://18655680.ngrok.io/atoms')
	     print r.json()
	 ````
 - **Inserir Dados**:
	 ````
	 def insert(id, name, numatom, description):
	     descricao = open(description)
	     descricao = descricao.read()
	     r = requests.post('http://18655680.ngrok.io/atom', data={'id': id,'element': name, 'numatom': numatom, 'description': descricao})
	     print r.status_code
	     print r.text 
	 ````
- **Deletar Dados**:
	````
	def delete(id):
	    link = 'http://18655680.ngrok.io/atom/' + id
	    r = requests.delete(link)
	    print r.status_code
	    print r.text
	````
- **Atualizar Dados**:
	````
	def atualizar(id, name, numatom, description):
	    descricao = open(description)
	    descricao = descricao.read()[:-1]
	    r = requests.patch('http://18655680.ngrok.io/atom/'+str(id), data={'id': id ,'element': name, 'numatom': numatom, 'description': descricao})
	    print r.status_code
	    print r.text
	````

- **Menu**:
	O menu é bem simples, tanto de utilização quanto de programação:
	![menu](https://i.imgur.com/meqDpJU.png)
	Todas as opções estão contidas nele, e as perguntas para entrada de dados são bem diretas então não há nenhum grande problema para usá-lo.

- **Diversidade**:
	O menu está disponível para **qualquer plataforma**, mesmo com ou sem python.
	Para **terminais** temos o script em Python 2.7: [Script Python](https://github.com/ProfessorJamesBach/ShowTheAtomServer/blob/master/mysql.py)
	Para quem **não tem o Python**, temos o arquivo compilado: [Arquivo .EXE](https://github.com/ProfessorJamesBach/ShowTheAtomServer/blob/master/mysql.exe)

