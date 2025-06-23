# projetor-enc

Projeto para controle de projetor com scripts e serviço systemd.

---

## Descrição

Este projeto fornece scripts para ligar, desligar e configurar projetores Epson em sistemas Linux, incluindo um serviço systemd para facilitar o gerenciamento.

---

## Estrutura do Projeto

```
.
├── usr/
│   ├── bin/
│   │   └── projetor-enc               # Script principal
│   ├── local/
│   │   └── bin/
│   │       └── projetor-enc-wrapper   # Wrapper para controle de tempo e logs
│   └── sbin/
│       └── epson-projector-cmd        # Binário proprietário Epson (não modificado)
├── etc/
│   └── systemd/
│       └── system/
│           └── projetor-enc.service   # Serviço systemd
├── debian/
│   ├── control                       # Arquivo de controle do pacote .deb
│   ├── postinst                     # Script pós-instalação
│   └── prerm                       # Script pré-removal
├── .github/
│   └── workflows/
│       └── build-deb.yml            # Workflow GitHub Actions para gerar .deb
└── README.md                       # Este arquivo
```

---

## Instalação

Para instalar o pacote `.deb` gerado:

```bash
sudo dpkg -i projetor-enc_1.0_all.deb
sudo systemctl enable projetor-enc.service
sudo systemctl start projetor-enc.service
```

---

## Uso

O script principal `projetor-enc` suporta os seguintes comandos:

- `start` — Liga o projetor
- `stop` — Desliga o projetor
- `restart` — Reinicia o projetor

O serviço `projetor-enc.service` usa um wrapper que implementa lógica de atraso e logging.

---

## Desenvolvimento

---

## Licença

Este projeto está licenciado sob a licença MIT, com exceção do arquivo:

- `/usr/sbin/epson-projector-cmd` — binário proprietário da Epson, não modificado, sem direitos de redistribuição.

Todos os arquivos do projeto devem manter os créditos originais ao autor **Elton Nike Casa - CANAL ENC**.

---

## Contato

Elton Nike Casa  
Email: eltonnikecasa@gmail.com  
Canal ENC

---

*Obrigado por utilizar o projetor-enc!*
