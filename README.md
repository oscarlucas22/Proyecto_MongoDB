# Comandos para MongoDB

## Iniciar MongoDB

    mongo
    
## Crear y si ya esta creada usar base de datos

    use 'NOMBRE_BD'
    
## Listar base de datos

    show dbs
    
## Verificar la base de datos actual

    db
    
## Eliminar base de datos

Hacerlo dentro de la base de datos

        db.dropDatabase()
    
## Importar json en MongoDB

Hacerlo fuera de mongo

        mongoimport --db NAME_BD --collection NAME_YOUR_COLLECTION --file 'ruta del json'
        
## Eliminar json de la base de datos

        db.NAME_COLLECTION.drop()
    
## Mostrar la coleccion

    db.NAME_COLLECTION.find().pretty
