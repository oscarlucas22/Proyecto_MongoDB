## CONSULTAS

#### Consultas Simples

* Haz una consulta que te muestre los que si son estudiantes de Hogwarts

		db.personajes.find({"estudianteDeHogwarts":true}).pretty()

* Haz una consulta que te muestre los estudiantes de Hogwarts de la casa Gryffindor

		db.personajes.find({"casaDeHogwarts":"Gryffindor"}).pretty()

* Haz una consulta que te muestre los personajes que no tienen hijos

		db.personajes.find({"hijos":[ ]}).pretty()

* Haz una consulta que te muestre las id que son mayores que 320

		db.personajes.find({"id":{$gt:320}}).pretty()

* Haz una consulta que te muestre si existe el hijo Ted Lupin

		db.personajes.find({"hijos":{$in:["Ted Lupin"]}}).pretty()


#### Consultas con arrays

* Haz una consulta que te muestre el padre y la madre de James Sirius Potter

		db.personajes.find({"hijos":{$all:["James Sirius Potter"]}}).pretty()

* Crea un array al personaje de apodo Harry donde se almacenarán la varita "Varita de Saúco"

		db.personajes.update({"apodo":"Harry"},{$push:{"varita":["Varita de Saúco"]}})

* Obtener todos los personajes que tengan como hechizo AVADA KEDAVRA

		db.personajes.find({"hechizos":{$all:["AVADA KEDAVRA"]}},{"personaje":1}).pretty()


#### Consultas con documentos embebidos

* Obten los apodos de los personajes que tengan como tipo de escoba la Nimbus

		db.personajes.find({"escobas.tipos":"Nimbus"},{"apodo":1}).pretty()

* Obtener el id de los personajes que tengan como casa de Hogwarts, Gryffindor

		db.personajes.find({"casaDeHogwarts":"Gryffindor"},{"id":1}).pretty()

* Obten el id del personaje que tenga como url de Wikipedia "https://en.wikipedia.org/wiki/Charlie"

		db.personajes.find({"metadata.sourceUrl":"https://en.wikipedia.org/wiki/Charlie"},{"id":1})


#### Consultas de agrupación

* Muestra todas las casas y cuantas veces se repiten

		db.personajes.aggregate([{$group:{_id:"$casaDeHogwarts","repetidos":{$sum:1}}}])

