# Defesa-Zabbix
### Sistema de monitoramento de infraestrutura da Defesa Civil de Mato Grosso utilizando Zabbix

#### Configuração obtida através da documentação oficial do Zabbix

    https://www.zabbix.com/documentation/current/manual/installation/containers

##### Para iniciar o serviço é necessário a configuração do docker-compose

    Apenas copie a sequência de comandos e cole no terminal:

    sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
    sudo chmod +x /usr/local/bin/docker-compose && \
    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

    Referência: https://docs.docker.com/compose/install/

##### Com o docker-compose instalado basta apenas inicar os serviços que foram configurados no docker-compose.yaml:

    Dentro do diretório ./Defesa-Zabbix:

    docker-compose up -d

##### Os serviços foram configurados sobre a rede interna 10.0.0.0/24, logo para acessar o serviço:

    Acessar no navegador:

    10.0.0.3:8080

#### Para efetuar o backup das informações do container

    sudo docker cp d983b7ca27f3:/data/wwwroot/zabbix ./backup/

