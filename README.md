# Docker Centos Systemd

[![](https://img.shields.io/docker/cloud/automated/code3tech/centos?label=build&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/code3tech/centos)
[![](https://img.shields.io/docker/cloud/build/code3tech/centos?label=status&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/code3tech/centos)
[![](https://img.shields.io/docker/image-size/code3tech/centos/7?label=size&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/code3tech/centos)
[![](https://img.shields.io/docker/pulls/code3tech/centos?label=pulls&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/code3tech/centos)
[![](https://img.shields.io/docker/stars/code3tech/centos?label=starts&logo=docker&logoColor=white)](https://hub.docker.com/repository/docker/code3tech/centos)
[![](https://img.shields.io/github/issues/code3tech/docker-centos-systemd?label=issues&logo=github&logoColor=white)](https://github.com/code3tech/docker-centos-systemd/issues)
[![](https://img.shields.io/github/license/code3tech/docker-centos-systemd?logo=github&logoColor=white)](https://github.com/code3tech/docker-centos-systemd/blob/main/LICENSE)

Este Dockerfile pode construir containers com a capacidade de usar o systemd, seu principal proposito é testar ansible playbooks e roles, simulando o SO alvo.

Branches
------------

Para facilitar a manutenção e atualização desses containers decidimos adotar uma estratégia de multiplas branches que refletem as versions do sistema operacional alvo. Dessa forma cada branch reflete uma versão do SO, como demostrado na tabela abaixo:

|Branch |CentOS Version|Docker image tag|
|-------|--------------|----------------|
|master |latest (8)    |8               |
|7      |7             |7               |

Pull strategy
------------

Cada branch nesse repositório tem um ciclo de vida individual, portanto **NÃO** se deve fazer merged.

Como Usar
------------

Rodando a última versão da imagem docker.

```
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  --volume /tmp:/tmp \
  code3tech/centos
```

Rodando uma versão específica da imagem docker.

```
docker run \
  --tty \
  --privileged \
  --volume /sys/fs/cgroup:/sys/fs/cgroup:ro \
  --volume /tmp:/tmp \
  code3tech/centos:7
``` 

Construindo seu própria imagem docker
------------

Para construir o sua própria imagem docker siga os seguintes passos:

  1. [Instale Docker](https://docs.docker.com/engine/installation/).
  2. Faça o clone do repositório para sua área de trabalho `git clone https://github.com/code3tech/docker-centos-systemd.git`
  3. Entre no diretório `cd docker-centos-systemd`
  4. Execute o commando para construir a imagem `docker build -t my-centos .`
  5. Execute o commando para rodar `docker run --tty --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:ro -v /tmp:/tmp my-centos`

Author
------------

Created in 2021 by [Code3 Tech](https://code3.tech/) 