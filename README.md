# Documentações e Comandos do Docker

O intuito dessa documentação é servir como consulta para usabilidade e resolução de problemas em projetos futuros.

## 🚀 Isolamentos do Container

* [PID](https://medium.com/@flaviochess/entendendo-os-containers-do-docker-a4a481007885) - Provê isolamento dos processos rodando dentro do container
* [NET](https://medium.com/@flaviochess/entendendo-os-containers-do-docker-a4a481007885) - Provê isolamento das interfaces de rede
* [IPC](https://medium.com/@flaviochess/entendendo-os-containers-do-docker-a4a481007885) - Provê isolamento da comunicação entre processos e memória compartilhada
* [MNT](https://medium.com/@flaviochess/entendendo-os-containers-do-docker-a4a481007885) - Provê isolamento do sistema de arquivos / pontos de montagem
* [UTS](https://medium.com/@flaviochess/entendendo-os-containers-do-docker-a4a481007885) - Provê isolamento do kernel. Age como se o container fosse outro host

## 🛠️ Composição Básica dos Comandos

Este é um exemplo básico de comandos do docker bem simples para visualização

```
run [OPTIONS] IMAGE [COMAND] [ARGS..]

docker run [IMAGE -> ubuntu] [COMMAND -> sleep 1d] - sobe o container e executa durante 1 dia

```

### ⚙️ Comandos de Visualização

```
docker ps | docker container ls - Lista todas as informações de imagens que estão em execução no momento
docker ps -a | docker container -a - Mostra todas as imagens que subiram no docker
docker images - visualização das imagens baixadas
docker history - histórico de imagens
```

### ⚙️ Comandos de Inicialização e Parada do Container

```
docker port [PID] -> visualização de mapeamento das portas do container
docker stop [PID] -> para a execução do container (para parar a execução do container leva 10s, caso queira que seja imediato use "docker stop -t=0 [PID]") 
docker start [PID] -> Inicializa o container
docker pause [PID] -> Pausar o container
docker unpause [PID] -> Despausa o container
docker rm [PID] -> Remove o container
```

### ⚙️ Comandos de Execução de Containers e Imagens

```
docker run [IMAGE -> ubuntu] [COMMAND -> sleep 1d] - sobe o container e executa durante 1 dia
docker run -it [IMAGE -> ubuntu] [COMMAND -> bach] - sobe o container e executa enquanto houver processos sendo executados, neste caso estamos entrando dentro do bach/terminal do container
docker run -d [IMAGE] -> sobe o container sem travar o terminal que está sendo usado
docker run -d -P [IMAGE] -> sobe o container sem travar o terminal e o próprio docker cria o mapeamento para outra porta
docker run -d -p 8080:80 [IMAGE] -> sobe o container sem travar o terminal indicando o mapeamento da porta de execução do container
docker exec -it [PID - processo] bash(comando) -> Executa uma interação com o container 
[-i = interação, t = terminal] [bash = comando], neste exemplo estamos entrando dentro da linha de comando
docker run -d -p 8080:3000 lfelipe/app-node:1.0 -> subindo o container com a nossa imagem criada na porta 8080
docker build -t lfelipe/app-node:1.0 . -> cria a imagem e nomeira (-t) a imagem com base no diretório atual
do container em execução 
```
