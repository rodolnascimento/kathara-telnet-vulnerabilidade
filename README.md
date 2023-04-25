Universidade Federal do Maranhão

**Segurança em Redes**

# Laboratório - *Telnet explorando vulnerabilidade*

## Objetivo 

O objetivo deste laboratório é explorar algumas vulnerabilidades em redes de computadores, especialmente em protocolos que não possuem nenhuma criptografia a exemplo do telnet, que é um protocolo usado para acesso remoto a hosts, mas como mencionando não possui nenhuma criptografia, o que pode ocasionar uma grave falha de segurança.

![Topologia de Rede][1]


## Laboratório -- Telnet


1.  Execute o comando *tcpdump* no *intruso:*

```bash
tcpdump -i eth0 -X dst <IP do pc1>
```

2.  No *pc1* crie um usuário  chamado *teste* usando o comando:

```bash
adduser teste
```

3.  execute o seguinte comando para fazer a ativação do serviço
    *telnet* no dispositivo PC1:

```bash
/etc/init.d/openbsd-inetd restart
```

4.  No *pc2* execute `telnet <IP do pc1>`. 
Repare como o *tcpdump* permite exibir a comunicação caracter por caracter em modo texto.

O comando *tcpdump* é um *sniffer* simples, que não possui interface gráfica ao contrário da ferramenta *Wireshark*.


5.  Conclusão: como podemos observar, o telnet expõe todo o conteúdo da comunicação, essa prática
é extremamente insegura e nunca deve ser usado em canais de comunicação inseguros, como por exemplo acesso a dispositivos fora da rede interna por meio da internet.
A alternativa segura recomendada é o *ssh* *secure shell*.


## Referências

- *Kathará*, [https://github.com/KatharaFramework/Kathara/wiki]

  [1]: media/image.png



