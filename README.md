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
docker run -it [IMAGE -> ubuntu] [COMMAND -> bach] - sobe o container e executa enquanto houver processos sendo executados, neste caso estamos entrando dentro do bach/terminal do container
docker run -d [IMAGE] -> sobe o container sem travar o terminal que está sendo usado
docker run -d -P [IMAGE] -> sobe o container sem travar o terminal e o próprio docker cria o mapeamento para outra porta
docker run -d -p 8080:80 [IMAGE] -> sobe o container sem travar o terminal indicando o mapeamento da porta de execução do container

```


## ⚙️ Comandos 
