# Monitoramento HP Laser MFP 432fdn — Zabbix

Este projeto surgiu da necessidade de monitorar o contador de páginas e os suprimentos da impressora HP Laser MFP 432fdn utilizando o Zabbix e o protocolo SNMP.

O objetivo é centralizar as informações da impressora no Zabbix, facilitando o acompanhamento do toner preto, da unidade de imagem e da estimativa de vida útil do fusor.

## Informações do projeto

- **Impressora:** HP Laser MFP 432fdn
- **Protocolo de monitoramento:** SNMPv2c
- **Plataforma:** Zabbix 7.4
- **Formato do template:** YAML

## O que é monitorado

O template inclui os seguintes itens:

- Contador total de páginas impressas;
- Percentual restante do toner preto;
- Percentual restante da unidade de imagem;
- Estimativa de vida útil restante do fusor.

### Como o modelo calcula os suprimentos

- **Toner preto:** percentual calculado a partir do valor SNMP recebido e da capacidade de referência de 15.000 páginas.
- **Unidade de imagem:** percentual calculado a partir do valor SNMP recebido e da capacidade de referência de 30.000 páginas.
- **Fusor:** estimativa calculada com base no contador total de páginas, considerando uma vida útil de referência de 90.000 páginas. Esse valor não é uma leitura direta do fusor via SNMP.

Essas capacidades são referências configuradas para este modelo e devem ser verificadas antes do uso em produção.

## Como instalar

1. Baixe o arquivo `template-hp-laser-mfp-432fdn.yaml` deste repositório.
2. Acesse a interface web do Zabbix.
3. Entre em **Coleta de dados → Templates**.
4. Clique em **Importar** e selecione o arquivo YAML.
5. Revise as opções de importação e conclua a operação.
6. Associe o template ao host da impressora.
7. Configure a interface SNMP do host com o endereço IP da impressora e a versão e comunidade SNMP utilizadas no seu ambiente.
8. Verifique se os itens estão recebendo dados corretamente.

> Antes de importar em um ambiente que já possua um template com o mesmo nome, revise as opções de atualização para evitar alterações indesejadas.

## Requisitos

- Zabbix 7.4 ou versão compatível;
- Impressora HP Laser MFP 432fdn com SNMP habilitado;
- Conectividade de rede entre o servidor ou proxy Zabbix e a impressora;
- Interface SNMP e comunidade configuradas corretamente no host.

## Observações

Este template foi desenvolvido especificamente para a HP Laser MFP 432fdn. O comportamento dos OIDs e os valores recebidos podem variar conforme o firmware e a implementação SNMP do equipamento.

Antes de utilizar o monitoramento em produção, compare os valores recebidos via SNMP com as informações exibidas no painel da própria impressora.

**Status do projeto:** em desenvolvimento. O template foi configurado e verificado no equipamento utilizado durante seu desenvolvimento; a importação em outros ambientes ainda precisa ser validada.

## Licença

Este projeto está licenciado sob a licença MIT.

Você pode usar, copiar, modificar e redistribuir este template, respeitando os termos da licença.
