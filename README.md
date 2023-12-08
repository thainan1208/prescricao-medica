# Prescrições Médicas Auto-Soberanas

### How to run

1. Clonar este repositório e descompactar o arquivo **aries-cloudagent-python-tcc.zip**

1. Clonar o repositório VON-Network:
```
git clone https://github.com/bcgov/von-network
cd von-network

```
3. Após entrar no diretório **von-network**, iniciar a rede Indy local:
```
./manage build
./manage start --logs

```
4. Em outro terminal, clonar o repositório **indy-tails-server** e executá-lo. Esse passo é necessário para revogar credenciais.
```
git clone https://github.com/bcgov/indy-tails-server.git
cd indy-tails-server/docker
./manage build
./manage start
```

5. Com **von-network** e **indy-tails-server** em execução, é possível inicar os agentes Aries do médico e paciente.
Em outro terminal, inicie o agente Aries do médico com:
```bash
cd aries-cloudagent-python-tcc/demo
./run_demo faber --revocation
```

Em outro terminal, inicie o agente Aries do paciente com:
```bash
cd aries-cloudagent-python-tcc/demo
./run_demo alice
```