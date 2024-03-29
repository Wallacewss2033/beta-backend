## Instalação com docker 

 - #### CASO NÃO QUEIRA USAR DOCKER [Clique aqui](https://github.com/Wallacewss2033/beta-bank)

- Clone o projeto
```
git clone git@github.com:Wallacewss2033/beta-backend.git
```
- Entre na raiz do prejeto ```beta-backend``` e clone o projeto ```beta-bank```
```
git clone git@github.com:Wallacewss2033/beta-bank.git
```

### Back-end
- ainda na pasta raíz do projeto ```beta-backend``` rode:
```
docker-compose up -d --build
```
- entre no terminal do container do projeto ```beta-bank``` 
 ```
 docker exec -it beta-bank bash
 ```
- no terminal do container rode:

```
composer install
```
- logo após rode esses comandos ```(fora do terminal do container)```
```
cp .env.example .env
```
```
php artisan key:generate
```

- Não esqueça de configurar o banco de dados na ``` .env ```
  
![image](https://github.com/Wallacewss2033/fullstack-challenge-20231205/assets/39920409/ec726dce-7762-4c68-b66c-668698afad41)

OBS: user e senha do mysql ambos são ```root```

- Volte para o terminal do container. Para criar o banco de dados rode:
```
php artisan migrate
```

- Para popular a tabela de accounts
```
php artisan db:seed
```
- Não esqueça de configurar o servidor extenal

![image](https://github.com/Wallacewss2033/beta-backend/assets/39920409/71114ff8-fc63-48e8-a5ab-c7077bf14adb)

- você pode testar a execução das tranfencias agendadas manualmente com o seguinte comando:
```
php artisan send:transactions
```

OBS: CASO HAJA ALGUM PROBLEMA DE PERMISSÃO NO PROJETO RODE:

```
chown -R root:www-data storage
```
```
chmod -R 777 ./storage
```
```
chmod -R 775 ./storage
```

### DOCUMENTAÇÃO

- A documentação foi criada no ```openapi 3.0.0```
- A documentação está em:

        - 📁 beta-backend
            - 📁 documentation
                - 📄 doc-beta-bank.yml


    ### Como usar:
    - baixe a extensão do vscode chamada 
        ```OpenAPI (Swagger) Editor```
    - abra o arquivo da documentação ```doc-beta-bank.yml```
    - click no icone no canto superior direito ou use o atalho (Shift+Alt+P)

        ![Alt text](image.png)
    
