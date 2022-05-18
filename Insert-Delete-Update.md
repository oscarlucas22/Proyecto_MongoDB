## INSERT

* Haz una inserccion de un solo personaje

	db.personajes.insertOne(
	{"personaje" : "Oscar Lucas",
	"apodo" : "Lucas",
	"estudianteDeHogwarts" : true,
	"casaDeHogwarts" : "Ravenclaw",
	"interpretado_por" : "Leonardo DiCaprio",
	"hijos" : [ ],
	"metadata" : {
			"sourceName" : "Wikipedia",
			"sourceUrl" : "https://en.wikipedia.org/wiki/"
		     },
	"imagen" : "",
	"escobas": {
        "tipos": [
            
        ]
    	},
    	"hechizos": [
        
    	]
    	})
* Haz una inserccion de varios(dos) personajes

		db.personajes.insertMany([
		{"personaje" : "Paco Diz",
		"apodo" : "Paquito",
		"estudianteDeHogwarts" : true,
		"casaDeHogwarts" : "Ravenclaw",
		"interpretado_por" : "Shaquille O'Neal",
		"hijos" : [ ],
		"metadata" : {
				"sourceName" : "Wikipedia",
				"sourceUrl" : "https://en.wikipedia.org/wiki/"
		     	},
		"imagen" : "No image",
		"escobas": {
        	"tipos": [
            
        	]
    		},
    		"hechizos": [
		
    		]
    		},
		{"personaje" : "Angel Suarez",
		"apodo" : "Suarez",
		"estudianteDeHogwarts" : true,
		"casaDeHogwarts" : "Ravenclaw",
		"interpretado_por" : "Jim Carrey",
		"hijos" : [ ],
		"metadata" : {
				"sourceName" : "Wikipedia",
				"sourceUrl" : "https://en.wikipedia.org/wiki/"
		    	 },
		"imagen" : "No image",
		"escobas": {
       		"tipos": [
            
    		]
    		},
    		"hechizos": [
        
    		]
    		}])


## DELETE

* Elimina el personaje con el apodo Filch
	
		db.personajes.deleteOne({"apodo": "Filch"})
	
* Elimina a los personajes que tengan en la imagen el mensaje de "No image"

		db.personajes.deleteMany({"imagen" : "No image"})


## UPDATE

* Actualiza el personaje Oscar Lucas y cambiale el apodo a Leo

		db.personajes.updateOne({"personaje":"Oscar Lucas"}, {$set:{"apodo":"Leo"}})
	
* Actualiza el personaje Remus Lupin y cambia el nombre del hijo Ted Lupin a Teddy Lupin

		db.personajes.updateMany({"personaje":"Remus Lupin"}, {$set:{"hijos":[ "Teddy Lupin" ]}})

