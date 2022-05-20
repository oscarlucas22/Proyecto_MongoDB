# Comandos para MongoDB

## Iniciar MongoDB

    mongo
    
## Crear y si ya esta creada usar base de datos

    use 'NOMBRE_BD'
    
## Listar base de datos

    show dbs
    
## Verificar la base de datos actual

    db
    
## Importar json en MongoDB

Hacerlo fuera de mongo

        mongoimport --db NAME_BD --collection NAME_YOUR_COLLECTION --file 'ruta del json'
    
## Eliminar base de datos

    db.NAME_COLLECTION.drop()
    
## Mostrar la coleccion

    db.NAME_COLLECTION.find().pretty
