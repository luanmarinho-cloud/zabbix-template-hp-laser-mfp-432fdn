# Monitoramento HP Laser MFP 432fdn — Zabbix

Este projeto surgiu da necessidade de acompanhar o funcionamento e os suprimentos da impressora HP Laser MFP 432fdn utilizando o Zabbix e o protocolo SNMP.

O objetivo é centralizar as informações da impressora no Zabbix, facilitando o acompanhamento do contador de páginas, do toner preto e da vida útil de componentes como o fusor e a unidade de imagem.

## Informações do projeto

- **Impressora:** HP Laser MFP 432fdn
- **Monitoramento:** SNMP
- **Plataforma:** Zabbix 7.4
- **Formato do template:** YAML

## O que é monitorado

O template foi criado com os seguintes itens:

- Contador total de páginas impressas;
- Nível do toner preto;
- Vida útil do fusor;
- Vida útil da unidade de imagem.

Os valores dos suprimentos dependem das informações disponibilizadas pela própria impressora via SNMP. As conversões para porcentagem precisam ser verificadas antes de utilizar o template em um ambiente de produção.

## Como importar o template

1. Baixe o arquivo YAML deste repositório.
2. Acesse o painel web do Zabbix.
3. Entre em **Coleta de dados → Templates**.
4. Clique em **Importar** e selecione o arquivo baixado.
5. Confira as opções e conclua a importação.
6. Associe o template ao host da impressora.
7. Configure a interface SNMP e a comunidade utilizada no seu ambiente.

Após a configuração, verifique se os itens estão recebendo dados corretamente.

## Requisitos

- Zabbix 7.4 ou versão compatível;
- HP Laser MFP 432fdn com SNMP habilitado;
- Servidor Zabbix com conectividade de rede até a impressora;
- Comunidade SNMP configurada corretamente.

## Observações

Este template foi desenvolvido para a HP Laser MFP 432fdn. Dependendo da configuração da impressora e da versão do firmware, alguns valores podem ser apresentados de maneira diferente.

Antes de utilizar o monitoramento de suprimentos em produção, confira os valores recebidos via SNMP e compare-os com as informações exibidas no painel da impressora.

**Projeto em desenvolvimento.**

## Licença

A licença será definida antes da distribuição pública do template.
