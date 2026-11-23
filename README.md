
# Linux Server + Pi-hole | Servidor DNS Local

## Sobre o projeto

Laboratório de infraestrutura desenvolvido para estudar a administração de servidores Linux, configuração de DNS e filtragem de domínios utilizando o Pi-hole.

O objetivo foi implementar um servidor DNS local capaz de processar consultas da rede, bloquear domínios de publicidade e disponibilizar estatísticas de consultas em um dashboard web.

## Tecnologias utilizadas

- Linux Server
- Distribuição: Ubuntu Linux
- Versão registrada: Ubuntu 26.04.1 LTS
- Pi-hole
- DNS
- SSH
- Terminal Linux
- nslookup
- Redes TCP/IP

## Arquitetura do laboratório

Cliente Windows
       |
       | Consulta DNS
       v
Servidor Linux
IP: 192.168.0.184
       |
       v
Pi-hole (DNS local)
       |
       |-- Domínio bloqueado: resposta 0.0.0.0 ou ::
       |
       |-- Domínio permitido: resolução DNS

## Implementação

O laboratório utiliza um servidor Linux com Pi-hole para fornecer resolução DNS e filtragem de domínios na rede local.

As verificações foram realizadas utilizando comandos no terminal Linux, direcionando consultas DNS para o endereço do servidor Pi-hole.

## Testes realizados

### 1. Consulta DNS

Comando utilizado:

```bash
nslookup google.com
```
Esse comando permite verificar a resolução de um domínio e identificar qual servidor DNS respondeu à consulta.

### 2. Teste de bloqueio DNS

Comando utilizado:

```bash
nslookup doubleclick.net 192.168.0.184
```

Resultado observado:

```text
Servidor:  pi.hole
Address:  192.168.0.184

Nome:    doubleclick.net
Addresses:  ::
          0.0.0.0
```

O resultado demonstra que o Pi-hole respondeu à consulta com endereços nulos, indicando o bloqueio do domínio.

### 3. Dashboard Pi-hole

O painel administrativo foi utilizado para visualizar as consultas DNS e acompanhar as estatísticas de filtragem.

## Evidências do laboratório

### Testes DNS
![Testes DNS](images/teste-dns.png)

### Bloqueio de domínio
![Bloqueio DNS](images/bloqueio-dns.png)

### Dashboard do Pi-hole
![Dashboard Pi-hole](images/dashboard-pihole.png)

> As imagens serão adicionadas à pasta `images` do repositório.

## Conhecimentos desenvolvidos

- Administração básica de serviços Linux
- Funcionamento da resolução DNS
- Configuração e utilização do Pi-hole
- Diagnóstico de consultas com nslookup
- Filtragem de domínios
- Análise de respostas DNS
- Monitoramento de consultas pelo dashboard


## Autor

Felipe Oliveira

Profissional de Tecnologia da Informação, formado em Análise e Desenvolvimento de Sistemas, com foco em Infraestrutura, Linux e Administração de Sistemas.

