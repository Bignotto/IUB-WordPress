`adduser deploy`
- inventar a senha
-  yes

`usermod -aG sudo deploy`

copiar a chave ssh para o novo usuário
- criar a pasta .ssh na home do novo usuario
- `cp ~/.ssh/authorized_keys /home/deploy/.ssh`
- `chmod 600 authorized_keys`
- `cd ..`
- `chmod 700 ./ssh`
- `chown -R deploy:deploy .ssh/`

instalando o docker
- `sudo apt-get install docker`

adicionar usuário deploy ao grupo dos usuários que podem rodar o docker
- `usermod -aG docker deploy`

