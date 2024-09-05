Instrucciones:

Ejecutar los siguientes comandos (En el root del proyecto)

npm install

Para compilar el JS file y modules (Este paso lo tiene que realizar cada vez que haga cambios al index.js):

npx webpack --config webpack.config.js

Una vez creado el bucket en S3, debe correr este comando para evitar problemas de CORS:

aws --endpoint-url=http://localhost:4566 s3api put-bucket-cors --bucket exam-bucket \
  --cors-configuration '{
    "CORSRules": [
      {
        "AllowedOrigins": ["*"],
        "AllowedMethods": ["GET", "POST", "PUT", "DELETE"],
        "AllowedHeaders": ["*"],
        "ExposeHeaders": []
      }
    ]
  }'

