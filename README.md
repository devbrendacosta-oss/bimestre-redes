# Comunicação de Dados e Redes de Computadores

Material de estudo da disciplina **Comunicação de Dados e Redes de Computadores**, do curso de Engenharia de Software da UNICEPLAC.

Esta documentação reúne os fundamentos teóricos, conceitos, protocolos, tecnologias e mecanismos utilizados na comunicação entre dispositivos e no funcionamento das redes de computadores.

O conteúdo está organizado por assuntos, com explicações, tabelas comparativas, exemplos práticos e referências bibliográficas.

---

## Sumário

1. [Comunicação de Dados e Redes](#1-comunicação-de-dados-e-redes)
2. [História e Classificação das Redes](#2-história-e-classificação-das-redes)
3. [Hardware e Infraestrutura de Redes](#3-hardware-e-infraestrutura-de-redes)
4. [Modelos OSI e TCP/IP](#4-modelos-osi-e-tcpip)
5. [Meios de Transmissão](#5-meios-de-transmissão)
6. [Cabeamento Estruturado](#6-cabeamento-estruturado)
7. [Ethernet e Comutação](#7-ethernet-e-comutação)
8. [Endereçamento IP: IPv4 e IPv6](#8-endereçamento-ip-ipv4-e-ipv6)
9. [Pacotes Locais e Remotos e Protocolo ARP](#9-pacotes-locais-e-remotos-e-protocolo-arp)
10. [Protocolo TCP](#10-protocolo-tcp)
11. [Protocolos UDP e RTP](#11-protocolos-udp-e-rtp)
12. [Protocolos e Serviços de Rede](#12-protocolos-e-serviços-de-rede)
13. [Wi-Fi, Bluetooth e WiMAX](#13-wi-fi-bluetooth-e-wimax)
14. [Sinais, Codificação, Modulação e Multiplexação](#14-sinais-codificação-modulação-e-multiplexação)
15. [Comutação por Circuitos e Pacotes](#15-comutação-por-circuitos-e-pacotes)
16. [Convergência de Redes e Internet das Coisas](#16-convergência-de-redes-e-internet-das-coisas)
17. [Funcionamento Integrado de uma Comunicação](#17-funcionamento-integrado-de-uma-comunicação)
18. [Referências Bibliográficas](#18-referências-bibliográficas)

---

# 1. Comunicação de Dados e Redes

## 1.1 Conceito de Comunicação de Dados

Comunicação de dados é o processo de transferência de informações entre dois ou mais dispositivos por meio de um canal de comunicação. Essas informações podem representar textos, imagens, vídeos, áudios, arquivos e outros tipos de dados.

Nos sistemas digitais, as informações são representadas por bits, ou seja, valores binários 0 e 1.

Para que a comunicação aconteça corretamente, os dispositivos precisam utilizar regras e protocolos que determinem como os dados serão organizados, transmitidos, recebidos e interpretados.

### Componentes da comunicação

| Componente | Função |
|---|---|
| Fonte | Dispositivo que origina a informação. |
| Transmissor | Prepara e codifica os dados para transmissão. |
| Canal | Meio pelo qual os sinais são transportados. |
| Receptor | Recebe os sinais e recupera os dados. |
| Destino | Dispositivo ou aplicação que utiliza a informação. |
| Protocolo | Conjunto de regras que organiza a comunicação. |

## 1.2 Características de uma comunicação eficiente

Uma comunicação eficiente depende de diferentes fatores:

- **Entrega:** os dados precisam chegar ao destinatário correto.
- **Precisão:** as informações devem chegar sem alterações indevidas.
- **Tempo:** os dados devem chegar dentro de um intervalo adequado à aplicação.
- **Jitter:** representa a variação do atraso entre pacotes sucessivos.
- **Latência:** corresponde ao tempo necessário para os dados percorrerem o caminho entre origem e destino.
- **Vazão (Throughput):** representa a quantidade efetiva de dados transmitidos em determinado período.
- **Largura de banda:** representa a capacidade de transmissão de um canal.

## 1.3 Modos de transmissão

| Modo | Funcionamento | Exemplo |
|---|---|---|
| Simplex | A comunicação acontece em apenas um sentido. | Transmissão tradicional de televisão. |
| Half-duplex | Os dois dispositivos podem transmitir, mas não simultaneamente. | Rádio comunicador. |
| Full-duplex | Os dispositivos transmitem e recebem simultaneamente. | Ligação telefônica e Ethernet moderna. |

A transmissão também pode ser serial ou paralela. Na transmissão serial, os bits são enviados sequencialmente. Na paralela, vários bits são enviados simultaneamente por diferentes linhas de comunicação.

---

# 2. História e Classificação das Redes

## 2.1 Evolução das redes de computadores

As redes de computadores surgiram da necessidade de compartilhar informações e recursos entre diferentes máquinas.

A ARPANET, criada em 1969, foi um dos primeiros projetos importantes de interligação de computadores por comutação de pacotes. Posteriormente, o desenvolvimento do TCP/IP possibilitou a comunicação entre redes diferentes, contribuindo para a formação da Internet.

A popularização da World Wide Web, na década de 1990, ampliou o acesso à informação e impulsionou o crescimento das redes. Atualmente, as redes sustentam serviços em nuvem, sistemas corporativos, comunicação móvel, plataformas digitais e dispositivos inteligentes.

### Internet, Web, Intranet e Extranet

- **Internet:** conjunto mundial de redes interconectadas que utilizam protocolos como IP.
- **Web:** serviço de páginas e aplicações acessado normalmente por navegadores usando HTTP ou HTTPS.
- **Intranet:** rede privada utilizada internamente por uma organização.
- **Extranet:** extensão controlada de recursos de uma rede privada para usuários externos autorizados.

## 2.2 Classificação das redes por abrangência

| Tipo | Descrição |
|---|---|
| PAN | Rede pessoal que conecta dispositivos próximos, como celulares e fones Bluetooth. |
| LAN | Rede local que conecta dispositivos em residências, laboratórios e empresas. |
| WLAN | Rede local sem fio, normalmente baseada em Wi-Fi. |
| CAN | Rede que interliga diferentes LANs dentro de um campus ou complexo empresarial. |
| MAN | Rede que atende uma área metropolitana ou cidade. |
| WAN | Rede de longa distância que conecta redes em regiões, países ou continentes. |

## 2.3 Topologias de rede

Topologia é a forma como os dispositivos e os enlaces de uma rede estão organizados.

- **Barramento:** todos os dispositivos compartilham um meio principal de comunicação. É uma estrutura simples, mas pode sofrer com colisões e falhas no cabo principal.
- **Estrela:** todos os dispositivos se conectam a um equipamento central, normalmente um switch. Facilita a expansão e a identificação de falhas.
- **Anel:** os dispositivos são organizados em um circuito fechado, no qual os dados percorrem os nós.
- **Malha:** possui múltiplas conexões entre os dispositivos, permitindo caminhos alternativos e maior redundância.
- **Árvore:** organiza os dispositivos hierarquicamente, formando ramificações.
- **Híbrida:** combina duas ou mais topologias em uma mesma infraestrutura.

A topologia física representa a disposição dos equipamentos e cabos. A topologia lógica representa a maneira como os dados circulam pela rede.

---

# 3. Hardware e Infraestrutura de Redes

## 3.1 Placa de Rede (NIC)

A NIC, ou Network Interface Card, é o componente responsável por conectar um dispositivo à rede.

Ela permite enviar e receber dados e implementa funções relacionadas às camadas física e de enlace. Cada interface Ethernet possui um endereço MAC utilizado na comunicação dentro do enlace local.

As interfaces podem utilizar diferentes tecnologias, como Ethernet cabeada, Wi-Fi e fibra óptica.

## 3.2 Equipamentos de rede

| Equipamento | Camada típica | Função |
|---|---|---|
| Repetidor | Física | Regenera ou retransmite sinais para ampliar o alcance. |
| Hub | Física | Repete os sinais recebidos para as demais portas. |
| Bridge | Enlace | Aprende endereços MAC e encaminha quadros entre segmentos. |
| Switch | Enlace | Encaminha quadros conforme os endereços MAC. |
| Roteador | Rede | Encaminha pacotes IP entre redes diferentes. |
| Access Point | Física e enlace | Conecta dispositivos sem fio à rede local. |
| Firewall | Diversas | Controla o tráfego conforme regras de segurança. |
| Modem/ONT | Física | Adapta a comunicação à tecnologia de acesso do provedor. |

## 3.3 Diferença entre Hub, Switch e Roteador

### Hub

O hub recebe um sinal em uma porta e o repete para as demais. Ele não analisa endereços MAC e não seleciona o destinatário.

Todos os dispositivos conectados compartilham o mesmo domínio de colisão, tornando esse equipamento menos eficiente em redes modernas.

### Switch

O switch trabalha principalmente na camada de enlace. Ele aprende os endereços MAC de origem dos quadros e associa esses endereços às portas pelas quais foram recebidos.

Quando recebe um quadro, consulta sua tabela MAC:

- Se conhece o destino, encaminha o quadro para a porta correspondente.
- Se não conhece o destino, realiza flooding dentro da VLAN.
- Se o destino estiver na mesma porta de entrada, pode filtrar o quadro.

### Roteador

O roteador trabalha na camada de rede e utiliza endereços IP para encaminhar pacotes entre redes diferentes.

Ele consulta sua tabela de roteamento, identifica o próximo salto e encaminha o pacote pelo caminho selecionado.

## 3.4 Domínios de colisão e broadcast

**Domínio de colisão:** região da rede na qual transmissões simultâneas podem provocar colisões. Hubs compartilham um domínio de colisão; switches separam domínios por porta.

**Domínio de broadcast:** conjunto de dispositivos que recebe quadros de broadcast de camada 2. Uma VLAN normalmente corresponde a um domínio de broadcast. Roteadores separam esses domínios.

A segmentação de redes reduz o alcance do tráfego de broadcast e melhora a organização da infraestrutura.

---

# 4. Modelos OSI e TCP/IP

## 4.1 Modelo OSI

O modelo OSI organiza a comunicação em sete camadas, permitindo compreender as funções necessárias para a transmissão de dados.

| Camada | Nome | Responsabilidade |
|---|---|---|
| 7 | Aplicação | Oferece serviços de rede às aplicações. |
| 6 | Apresentação | Trata representação, codificação, compressão e criptografia. |
| 5 | Sessão | Gerencia o estabelecimento e a coordenação das sessões. |
| 4 | Transporte | Controla a comunicação entre processos. |
| 3 | Rede | Realiza endereçamento lógico e roteamento. |
| 2 | Enlace | Organiza quadros e utiliza endereços MAC. |
| 1 | Física | Transmite bits por sinais elétricos, ópticos ou de rádio. |

### Funções das camadas

**Aplicação:** oferece serviços utilizados por programas, como navegação, transferência de arquivos e resolução de nomes.

**Apresentação:** define como os dados são representados e pode realizar codificação, compressão e criptografia.

**Sessão:** organiza o diálogo entre aplicações e pode controlar o estabelecimento, a sincronização e o encerramento de sessões.

**Transporte:** permite a comunicação entre processos por meio de portas. TCP e UDP são exemplos de protocolos dessa camada.

**Rede:** realiza o endereçamento lógico e determina caminhos entre redes. O protocolo IP é seu principal exemplo.

**Enlace:** organiza os dados em quadros e controla a entrega dentro do enlace local. Ethernet é uma tecnologia dessa camada.

**Física:** trata da transmissão dos bits pelo meio físico, incluindo cabos, conectores, frequências e sinais.

## 4.2 Modelo TCP/IP

O modelo TCP/IP representa a arquitetura prática utilizada na Internet.

| Camada TCP/IP | Funções | Exemplos |
|---|---|---|
| Aplicação | Serviços utilizados pelas aplicações. | HTTP, DNS, DHCP e SMTP. |
| Transporte | Comunicação entre processos. | TCP e UDP. |
| Internet | Endereçamento e encaminhamento de pacotes. | IPv4 e IPv6. |
| Acesso à Rede | Comunicação no enlace e transmissão física. | Ethernet e Wi-Fi. |

## 4.3 Encapsulamento

O encapsulamento acontece quando cada camada adiciona informações de controle aos dados recebidos da camada superior.

| Camada | Unidade de dados |
|---|---|
| Aplicação | Dados |
| Transporte | Segmento TCP ou datagrama UDP |
| Rede | Pacote ou datagrama IP |
| Enlace | Quadro |
| Física | Bits ou símbolos |

No destino, acontece o desencapsulamento: cada camada interpreta e remove as informações correspondentes, entregando os dados à camada superior.

Uma distinção importante é que o endereço IP identifica a origem e o destino lógico, enquanto o endereço MAC identifica interfaces no enlace atual. Ao atravessar roteadores, o quadro de enlace é recriado para cada novo enlace.

---

# 5. Meios de Transmissão

Os meios de transmissão são os canais utilizados para transportar sinais entre dispositivos.

## 5.1 Meios guiados

São aqueles em que os sinais percorrem um meio físico delimitado.

| Meio | Características |
|---|---|
| Par trançado | Utiliza pares de fios de cobre trançados para reduzir interferências. |
| Cabo coaxial | Possui condutor central, isolante e blindagem. |
| Fibra óptica | Transmite informações por pulsos de luz, oferecendo alta capacidade e imunidade à interferência eletromagnética. |

### Par trançado

É bastante utilizado em redes Ethernet. Os pares são trançados para reduzir interferências eletromagnéticas e diafonia.

Categorias comuns incluem Cat 5e, Cat 6 e Cat 6A, que possuem características de desempenho distintas.

### Fibra óptica

Utiliza luz para transportar informações por um núcleo óptico.

- **Multimodo:** permite diferentes modos de propagação e costuma ser utilizada em distâncias menores.
- **Monomodo:** possui núcleo menor e é adequada para enlaces de maior distância.

A fibra oferece elevada capacidade de transmissão e não sofre interferência eletromagnética como os cabos de cobre.

## 5.2 Meios não guiados

Utilizam ondas eletromagnéticas propagadas pelo espaço.

Exemplos:

- Rádio.
- Micro-ondas.
- Infravermelho.
- Comunicação via satélite.

O desempenho depende de fatores como frequência, potência, obstáculos, interferência e posicionamento das antenas.

## 5.3 Problemas de transmissão

- **Atenuação:** redução da potência do sinal ao longo do meio.
- **Ruído:** presença de sinais indesejados que interferem na comunicação.
- **Interferência:** influência de outros sinais sobre a transmissão.
- **Distorção:** alteração da forma original do sinal.
- **Diafonia:** interferência entre pares de cabos próximos.

---

# 6. Cabeamento Estruturado

Cabeamento estruturado é uma infraestrutura organizada e padronizada de cabos, conectores, tomadas, painéis e espaços técnicos que permite conectar diferentes equipamentos de uma organização.

## 6.1 Subsistemas

- **Área de trabalho:** local onde os dispositivos dos usuários são conectados.
- **Cabeamento horizontal:** liga as tomadas da área de trabalho à sala de telecomunicações.
- **Backbone:** interliga salas de telecomunicações e equipamentos principais.
- **Sala de telecomunicações:** concentra equipamentos e terminações de cabos.
- **Sala de equipamentos:** abriga equipamentos centrais da infraestrutura.
- **Entrada de edifício:** ponto de entrada dos serviços externos de telecomunicações.

## 6.2 Padrões T568A e T568B

Os padrões T568A e T568B definem a disposição dos pares de fios nos conectores RJ-45.

| Pino | T568A | T568B |
|---|---|---|
| 1 | Branco/verde | Branco/laranja |
| 2 | Verde | Laranja |
| 3 | Branco/laranja | Branco/verde |
| 4 | Azul | Azul |
| 5 | Branco/azul | Branco/azul |
| 6 | Laranja | Verde |
| 7 | Branco/marrom | Branco/marrom |
| 8 | Marrom | Marrom |

### Tipos de cabos

- **Cabo direto:** utiliza o mesmo padrão nas duas extremidades, A-A ou B-B.
- **Cabo cruzado:** utiliza T568A em uma extremidade e T568B na outra.

Equipamentos modernos frequentemente possuem Auto-MDI/MDIX, que detecta e ajusta automaticamente a configuração de transmissão e recepção.

---

# 7. Ethernet e Comutação

## 7.1 Conceito de Ethernet

Ethernet é uma família de tecnologias de redes locais padronizada pelo IEEE 802.3.

Ela define características relacionadas à transmissão física, aos quadros, aos endereços MAC e à comunicação entre dispositivos em uma rede local.

## 7.2 Endereço MAC

O endereço MAC identifica uma interface de rede no enlace local.

Um endereço MAC Ethernet tradicional possui 48 bits, representados por 6 bytes em hexadecimal.

Exemplo:

`00:1A:2B:3C:4D:5E`

O MAC é utilizado para encaminhar quadros dentro da rede local. Ele não substitui o endereço IP, que identifica logicamente os dispositivos na comunicação entre redes.

## 7.3 Estrutura do quadro Ethernet

| Campo | Função |
|---|---|
| Preâmbulo | Auxilia a sincronização entre emissor e receptor. |
| SFD | Indica o início do quadro. |
| MAC de destino | Identifica a interface destinatária no enlace. |
| MAC de origem | Identifica a interface emissora. |
| Tipo/Comprimento | Identifica o protocolo encapsulado ou o tamanho dos dados. |
| Payload | Transporta os dados. |
| FCS | Detecta erros por meio de verificação CRC. |

Na Ethernet tradicional, o quadro possui tamanho mínimo de 64 bytes e máximo de 1518 bytes, sem considerar preâmbulo e SFD. A inclusão de uma tag VLAN 802.1Q acrescenta 4 bytes.

## 7.4 Tipos de transmissão

- **Unicast:** envia dados para um destinatário específico.
- **Broadcast:** envia dados para todos os dispositivos do domínio de broadcast.
- **Multicast:** envia dados para um grupo específico de dispositivos.

## 7.5 VLAN

VLAN é uma tecnologia que permite dividir logicamente uma rede física em redes virtuais independentes.

Cada VLAN forma um domínio de broadcast separado.

As portas podem ser configuradas como:

- **Access:** associam o tráfego de um dispositivo final a uma VLAN.
- **Trunk:** transportam múltiplas VLANs entre equipamentos, normalmente utilizando a marcação IEEE 802.1Q.

A comunicação entre VLANs exige roteamento de camada 3.

---

# 8. Endereçamento IP: IPv4 e IPv6

## 8.1 Protocolo IP

O Internet Protocol é responsável pelo endereçamento lógico e pelo encaminhamento de pacotes entre redes.

O IP utiliza o modelo de melhor esforço (*best effort*), ou seja, não garante sozinho que os pacotes chegarão ao destino, na ordem correta ou sem perdas.

## 8.2 IPv4

O IPv4 utiliza endereços de 32 bits, divididos em quatro octetos.

Exemplo:

`192.168.10.25`

Cada octeto pode representar um valor de 0 a 255.

## 8.3 Máscara de sub-rede

A máscara determina quais bits de um endereço IP identificam a rede e quais identificam os dispositivos.

Exemplo:

- Endereço IP: `192.168.10.25`
- Máscara: `255.255.255.0`
- Prefixo: `/24`

Nesse caso, os primeiros 24 bits representam a rede e os últimos 8 bits identificam os hosts.

## 8.4 CIDR e subnetting

CIDR permite representar redes utilizando um prefixo, como `/24`, `/26` ou `/30`.

O subnetting consiste em dividir uma rede maior em redes menores, permitindo melhor organização e utilização dos endereços IP.

A quantidade convencional de hosts utilizáveis é calculada por:

`2^h - 2`

Onde `h` representa a quantidade de bits destinados aos hosts. Essa regra possui exceções, como prefixos `/31` e `/32`.

### Tabela de sub-redes

| Prefixo | Máscara | Total de endereços | Hosts usuais |
|---|---|---:|---:|
| /24 | 255.255.255.0 | 256 | 254 |
| /25 | 255.255.255.128 | 128 | 126 |
| /26 | 255.255.255.192 | 64 | 62 |
| /27 | 255.255.255.224 | 32 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /29 | 255.255.255.248 | 8 | 6 |
| /30 | 255.255.255.252 | 4 | 2 |

### Exemplo de cálculo

Considere o endereço:

`192.168.10.70/26`

A máscara correspondente é:

`255.255.255.192`

O tamanho do bloco é calculado por:

`256 - 192 = 64`

Os blocos são:

- 192.168.10.0 até 192.168.10.63
- 192.168.10.64 até 192.168.10.127
- 192.168.10.128 até 192.168.10.191
- 192.168.10.192 até 192.168.10.255

O endereço `192.168.10.70` pertence ao segundo bloco.

| Informação | Endereço |
|---|---|
| Rede | 192.168.10.64 |
| Primeiro host | 192.168.10.65 |
| Último host | 192.168.10.126 |
| Broadcast | 192.168.10.127 |

## 8.5 Gateway padrão

O gateway padrão é o dispositivo utilizado para encaminhar pacotes destinados a outras redes.

Quando um computador identifica que o destino não pertence à sua sub-rede, ele encaminha o pacote ao roteador configurado como gateway.

O IP de destino continua sendo o endereço do dispositivo final. O MAC de destino do quadro Ethernet, entretanto, será o MAC da interface local do gateway.

## 8.6 IPv6

O IPv6 foi desenvolvido para ampliar o espaço de endereçamento disponível e oferecer uma arquitetura de endereçamento mais ampla.

Utiliza endereços de 128 bits, representados por oito grupos hexadecimais chamados hextetos.

Exemplo:

`2001:0db8:0000:1111:0000:0000:0000:0200`

### Regras de abreviação

1. Os zeros à esquerda de cada hexteto podem ser removidos.
2. Uma sequência contínua de hextetos com valor zero pode ser substituída por `::`.
3. A abreviação `::` pode aparecer apenas uma vez no mesmo endereço.

Forma abreviada:

`2001:db8:0:1111::200`

### Diferenças entre IPv4 e IPv6

| Característica | IPv4 | IPv6 |
|---|---|---|
| Tamanho | 32 bits | 128 bits |
| Representação | Decimal | Hexadecimal |
| Separador | Ponto | Dois-pontos |
| Broadcast | Possui | Não possui |
| Resolução de vizinhos | ARP | NDP |
| Fragmentação por roteadores | Pode ocorrer | Não ocorre nos roteadores |

---

# 9. Pacotes Locais e Remotos e Protocolo ARP

## 9.1 Comunicação local e remota

Quando um dispositivo deseja enviar informações para outro, precisa identificar se o destino está na mesma rede local ou em uma rede diferente.

Essa decisão é realizada utilizando o endereço IP, a máscara de sub-rede e a tabela de roteamento.

### Comunicação local

Quando o destino pertence à mesma sub-rede, o dispositivo envia o quadro diretamente ao MAC do destinatário.

Exemplo:

- Origem: `192.168.1.10/24`
- Destino: `192.168.1.20/24`

Como ambos pertencem à rede `192.168.1.0/24`, a comunicação acontece diretamente pela rede local.

### Comunicação remota

Quando o destino pertence a outra rede, o dispositivo encaminha o pacote ao gateway padrão.

Exemplo:

- Origem: `192.168.1.10/24`
- Destino: `8.8.8.8`

Como o endereço de destino não pertence à rede local, o quadro Ethernet será enviado ao MAC do gateway.

| Situação | MAC de destino no quadro | IP de destino |
|---|---|---|
| Destino local | MAC do dispositivo final | IP do dispositivo final |
| Destino remoto | MAC do gateway | IP do servidor remoto |

## 9.2 Protocolo ARP

ARP significa *Address Resolution Protocol* e é utilizado em redes IPv4 para descobrir o endereço MAC associado a um endereço IP no enlace local.

Quando um dispositivo precisa enviar um quadro para um endereço IPv4 e não conhece o MAC correspondente, consulta primeiro sua tabela ARP.

Se não encontrar uma entrada válida, envia uma mensagem ARP Request em broadcast.

O dispositivo que possui o endereço IP solicitado responde com um ARP Reply, normalmente em unicast, informando seu endereço MAC.

O emissor armazena temporariamente essa associação para utilizar nas próximas comunicações.

### Funcionamento do ARP

1. O dispositivo identifica o endereço IP do próximo salto.
2. Consulta sua tabela ARP.
3. Caso não encontre o MAC, envia um ARP Request.
4. O dispositivo correspondente responde com ARP Reply.
5. A associação IP-MAC é armazenada no cache.
6. O quadro Ethernet é transmitido utilizando o MAC descoberto.

## 9.3 Tabela ARP

A tabela ARP mantém associações entre endereços IPv4 e endereços MAC conhecidos.

As entradas podem ser dinâmicas, aprendidas automaticamente, ou estáticas, configuradas manualmente.

Comandos de consulta:

**Windows:**

```bash
arp -a
```

**Linux:**

```bash
ip neigh show
```

A tabela ARP representa os vizinhos conhecidos no contexto local, não todos os dispositivos existentes na Internet.

## 9.4 Segurança ARP

O ARP não possui autenticação criptográfica das respostas. Por isso, pode ser explorado em ataques conhecidos como ARP Spoofing ou ARP Poisoning.

Nesse tipo de ataque, um dispositivo envia informações falsas para associar o IP de outro equipamento, como o gateway, ao MAC do atacante.

Isso pode permitir interceptação, alteração ou interrupção do tráfego local.

Medidas de proteção incluem segmentação, segurança de portas, monitoramento e Dynamic ARP Inspection em equipamentos compatíveis.

---

# 10. Protocolo TCP

## 10.1 Conceito

TCP significa *Transmission Control Protocol*. É um protocolo da camada de transporte que oferece comunicação orientada à conexão, confiável e ordenada entre aplicações.

Ele utiliza números de sequência, confirmações, retransmissões, controle de fluxo e controle de congestionamento para garantir que o fluxo de bytes seja entregue corretamente.

## 10.2 Segmento TCP

O segmento TCP possui um cabeçalho com informações utilizadas no controle da comunicação.

| Campo | Função |
|---|---|
| Porta de origem | Identifica o processo emissor. |
| Porta de destino | Identifica o processo receptor. |
| Sequence Number | Indica a posição dos dados no fluxo. |
| Acknowledgment Number | Indica o próximo byte esperado. |
| Window Size | Informa a janela de recepção anunciada. |
| Checksum | Detecta corrupção dos dados e do cabeçalho. |
| SYN | Inicia a sincronização da conexão. |
| ACK | Indica uma confirmação válida. |
| FIN | Solicita encerramento ordenado de um sentido. |
| RST | Reinicia ou rejeita uma conexão. |
| PSH | Solicita disponibilização dos dados à aplicação sem atraso desnecessário. |
| URG | Indica a presença de dados urgentes. |

## 10.3 Three-Way Handshake

O estabelecimento de uma conexão TCP acontece, tradicionalmente, em três etapas.

| Etapa | Mensagem | Funcionamento |
|---|---|---|
| 1 | SYN | O cliente solicita a abertura da conexão e informa seu número inicial de sequência. |
| 2 | SYN + ACK | O servidor responde, informa seu número inicial e confirma o SYN do cliente. |
| 3 | ACK | O cliente confirma a resposta do servidor. |

Após essas três etapas, a conexão está estabelecida e os dados podem ser transmitidos.

Durante a abertura, os dispositivos também podem negociar parâmetros como MSS, Window Scale e SACK.

## 10.4 Números de sequência e confirmações

O TCP trabalha com números de sequência associados aos bytes transmitidos.

O número de sequência identifica a posição do primeiro byte de dados de um segmento.

O número de confirmação indica o próximo byte que o receptor espera receber.

Exemplo:

Se o receptor recebeu corretamente os bytes até a posição 499, poderá enviar:

`ACK = 500`

Isso significa que espera receber o byte 500.

Caso ocorra perda de dados, o TCP pode realizar retransmissões para recuperar as informações.

## 10.5 Janela de recepção

A janela de recepção, chamada *Receive Window* (rwnd), informa ao emissor quanto espaço o receptor possui disponível para armazenar dados.

Ela permite controlar a quantidade de informações transmitidas sem confirmação, evitando que o emissor envie mais dados do que o receptor consegue receber e armazenar.

## 10.6 Janela de transmissão e controle de congestionamento

O TCP utiliza mecanismos para controlar a quantidade de dados enviados antes de receber confirmações.

A janela de congestionamento, chamada *Congestion Window* (cwnd), controla o volume de dados que pode permanecer em trânsito sem confirmação, considerando as condições da rede.

O limite efetivo de transmissão é influenciado pela menor entre a janela de recepção e a janela de congestionamento:

`Limite efetivo = min(rwnd, cwnd)`

A janela de recepção protege o dispositivo receptor. A janela de congestionamento ajuda a evitar sobrecarga na rede.

## 10.7 Encerramento da conexão

O encerramento ordenado utiliza mensagens FIN e ACK.

Como a comunicação TCP é bidirecional, cada lado pode encerrar seu sentido de transmissão independentemente do outro.

A flag RST é utilizada para interromper ou rejeitar uma conexão de forma abrupta.

---

# 11. Protocolos UDP e RTP

## 11.1 UDP

UDP significa *User Datagram Protocol*. É um protocolo de transporte sem conexão, com cabeçalho simples e baixo overhead.

Diferentemente do TCP, não oferece mecanismos nativos de confirmação, retransmissão ou garantia de entrega e ordenação.

Seu cabeçalho contém:

- Porta de origem.
- Porta de destino.
- Comprimento.
- Checksum.

É utilizado em aplicações nas quais a baixa latência e a simplicidade são importantes, como consultas DNS, jogos e determinadas aplicações de mídia em tempo real.

## 11.2 Comparação entre TCP e UDP

| Característica | TCP | UDP |
|---|---|---|
| Conexão | Orientado à conexão | Sem conexão |
| Entrega | Confiável | Não garante entrega |
| Ordenação | Garante ordem do fluxo | Não garante ordem |
| Retransmissão | Possui | Não possui nativamente |
| Controle de fluxo | Possui | Não possui equivalente nativo |
| Uso | Web, arquivos e serviços que exigem confiabilidade | DNS, jogos e mídia em tempo real |

## 11.3 RTP

RTP significa *Real-time Transport Protocol* e é utilizado para transportar áudio e vídeo em tempo real.

Seu cabeçalho inclui informações como:

- Número de sequência.
- Timestamp.
- Identificador da fonte.

Esses campos ajudam a identificar perdas, reconstruir a ordem dos pacotes e sincronizar fluxos de mídia.

RTP normalmente funciona sobre UDP, mas não garante sozinho a entrega dos pacotes ou a qualidade do serviço.

---

# 12. Protocolos e Serviços de Rede

## 12.1 DNS

DNS significa *Domain Name System* e é responsável por traduzir nomes de domínio em endereços IP.

Quando um usuário acessa um site pelo navegador, o DNS permite localizar o endereço IP associado ao nome utilizado.

O sistema possui estrutura hierárquica, envolvendo servidores raiz, servidores de domínio de topo (TLD) e servidores autoritativos.

### Principais registros DNS

| Registro | Função |
|---|---|
| A | Associa um nome a um endereço IPv4. |
| AAAA | Associa um nome a um endereço IPv6. |
| MX | Identifica servidores responsáveis pelo recebimento de e-mails. |
| CNAME | Cria um alias para outro nome de domínio. |
| NS | Identifica servidores de nomes de uma zona. |

O DNS utiliza normalmente a porta 53, por UDP ou TCP.

## 12.2 DHCP

DHCP significa *Dynamic Host Configuration Protocol* e automatiza a configuração de endereços IP nos dispositivos.

Ele pode fornecer:

- Endereço IP.
- Máscara de sub-rede.
- Gateway padrão.
- Servidores DNS.
- Tempo de concessão do endereço.

### Processo DORA

O DHCPv4 utiliza quatro etapas principais:

| Etapa | Mensagem | Função |
|---|---|---|
| 1 | Discover | Cliente procura servidores DHCP. |
| 2 | Offer | Servidor oferece parâmetros de rede. |
| 3 | Request | Cliente solicita a oferta. |
| 4 | Acknowledge | Servidor confirma a configuração. |

O processo é conhecido como DORA: Discover, Offer, Request e Acknowledge.

## 12.3 HTTP e HTTPS

HTTP significa *Hypertext Transfer Protocol* e é utilizado para transferir recursos e informações entre clientes e servidores Web.

Uma requisição HTTP pode conter método, caminho, cabeçalhos e corpo. A resposta contém código de status, cabeçalhos e conteúdo.

HTTPS é HTTP protegido por TLS, oferecendo confidencialidade, integridade e autenticação do servidor.

## 12.4 Protocolos de e-mail

- **SMTP:** utilizado para envio e encaminhamento de mensagens.
- **POP3:** permite acessar mensagens armazenadas no servidor, geralmente com foco em recuperação.
- **IMAP:** permite sincronizar mensagens, pastas e estados entre dispositivos e servidor.

## 12.5 Firewall

Firewall é um mecanismo de segurança que controla o tráfego de entrada e saída da rede com base em regras.

As regras podem considerar:

- Endereço IP de origem e destino.
- Protocolo utilizado.
- Portas.
- Estado da conexão.
- Conteúdo do tráfego, dependendo da tecnologia.

Firewalls com estado acompanham conexões e podem permitir o tráfego de retorno relacionado a sessões autorizadas.

## 12.6 Proxy

Proxy é um intermediário entre clientes e servidores.

Pode ser utilizado para controlar acesso, autenticar usuários, registrar solicitações e armazenar conteúdos em cache.

O proxy reverso fica diante de servidores e recebe conexões externas, podendo distribuir solicitações para diferentes serviços internos.

### Portas comuns

| Serviço | Porta |
|---|---|
| HTTP | TCP 80 |
| HTTPS | TCP 443 |
| DNS | UDP/TCP 53 |
| DHCPv4 | UDP 67 e 68 |
| SSH | TCP 22 |
| SMTP | TCP 25 e 587 |
| POP3 | TCP 110 |
| IMAP | TCP 143 |
| POP3 com TLS | TCP 995 |
| IMAP com TLS | TCP 993 |

---

# 13. Wi-Fi, Bluetooth e WiMAX

## 13.1 Wi-Fi

Wi-Fi é uma tecnologia de rede local sem fio baseada na família de padrões IEEE 802.11.

Os dispositivos conectam-se normalmente por meio de um ponto de acesso, que coordena a comunicação com a rede local.

O desempenho depende de fatores como:

- Distância do ponto de acesso.
- Obstáculos físicos.
- Interferência de outros equipamentos.
- Frequência utilizada.
- Largura do canal.
- Quantidade de dispositivos conectados.

O Wi-Fi utiliza mecanismos de acesso ao meio como CSMA/CA, que busca evitar colisões no meio sem fio.

A segurança deve utilizar mecanismos atuais, como WPA2-AES ou WPA3.

## 13.2 Bluetooth

Bluetooth é uma tecnologia de comunicação sem fio de curto alcance, utilizada para conectar periféricos e dispositivos pessoais.

O Bluetooth Classic atende aplicações tradicionais, enquanto o Bluetooth Low Energy (BLE) foi desenvolvido para reduzir o consumo energético, sendo utilizado em sensores, dispositivos vestíveis e aplicações de IoT.

## 13.3 WiMAX

WiMAX está associado ao padrão IEEE 802.16 e foi desenvolvido para oferecer acesso banda larga sem fio em áreas maiores do que as atendidas por uma WLAN convencional.

---

# 14. Sinais, Codificação, Modulação e Multiplexação

## 14.1 Sinais analógicos e digitais

Um sinal analógico varia continuamente ao longo do tempo. Um sinal digital representa informações por níveis discretos.

Nos sistemas digitais, os bits são convertidos em sinais adequados ao meio de transmissão por meio de técnicas de codificação.

## 14.2 Codificação de linha

A codificação de linha define como os bits serão representados fisicamente.

- **NRZ:** representa os bits por níveis de sinal, sem necessariamente retornar a zero entre eles.
- **Manchester:** utiliza uma transição no meio de cada intervalo de bit, facilitando a sincronização.
- **Códigos de bloco:** convertem grupos de bits em padrões que atendem a determinadas características de transmissão.

## 14.3 Modulação

Modulação é o processo de modificar uma característica de uma onda portadora para transportar informações.

| Técnica | Característica modificada |
|---|---|
| ASK | Amplitude |
| FSK | Frequência |
| PSK | Fase |
| QPSK | Utiliza quatro estados de fase e representa dois bits por símbolo. |

Modulações mais complexas podem transportar mais bits por símbolo, mas geralmente exigem melhores condições de sinal.

## 14.4 Multiplexação

Multiplexação permite compartilhar um mesmo meio de transmissão entre diferentes sinais ou fluxos de dados.

| Técnica | Funcionamento |
|---|---|
| FDM | Divide o canal em faixas de frequência. |
| TDM | Divide o uso do canal em intervalos de tempo. |
| WDM | Utiliza diferentes comprimentos de onda em uma fibra óptica. |
| CDM/CDMA | Separa transmissões por códigos diferentes. |

No destino, ocorre a demultiplexação, que separa os fluxos recebidos.

## 14.5 Capacidade de transmissão: Nyquist e Shannon

### Fórmula de Nyquist

`C = 2B × log₂(M)`

Onde:

- C = capacidade máxima teórica em bits por segundo.
- B = largura de banda em hertz.
- M = quantidade de níveis de sinal.

A fórmula considera um canal ideal sem ruído.

### Fórmula de Shannon

`C = B × log₂(1 + S/N)`

Onde:

- C = capacidade máxima teórica.
- B = largura de banda.
- S/N = relação sinal-ruído em escala linear.

A fórmula considera os limites de capacidade de um canal com ruído.

## 14.6 Erros de transmissão

Erros podem ocorrer por ruído, interferência, atenuação, distorção ou problemas de sincronização.

Alguns mecanismos utilizados para detectar ou corrigir erros são:

- Paridade.
- Checksum.
- CRC.
- FEC.
- ARQ.

O CRC é utilizado para detectar alterações nos dados transmitidos. O FEC acrescenta redundância para permitir correção no receptor. O ARQ utiliza confirmações e retransmissões para recuperar informações perdidas ou corrompidas.

---

# 15. Comutação por Circuitos e Pacotes

## 15.1 Comutação por circuitos

Na comutação por circuitos, um caminho de comunicação é estabelecido entre os participantes e os recursos podem ficar reservados durante a comunicação.

Esse modelo foi tradicionalmente utilizado em sistemas de telefonia.

## 15.2 Comutação por pacotes

Na comutação por pacotes, os dados são divididos em unidades menores, chamadas pacotes.

Cada pacote possui informações de controle e conteúdo. Os roteadores analisam os endereços de destino e encaminham os pacotes para o próximo salto.

Diferentes comunicações podem compartilhar os mesmos enlaces, permitindo melhor aproveitamento dos recursos.

### Comparação

| Característica | Circuitos | Pacotes |
|---|---|---|
| Caminho | Circuito estabelecido previamente | Pacotes encaminhados pela rede |
| Recursos | Podem ficar reservados | São compartilhados |
| Atraso | Pode ser mais previsível após o estabelecimento | Pode variar conforme congestionamento |
| Utilização | Telefonia tradicional | Internet e redes de dados |

---

# 16. Convergência de Redes e Internet das Coisas

## 16.1 Convergência de redes

Convergência é a utilização de uma infraestrutura comum para transportar diferentes tipos de comunicação, como dados, voz, vídeo e automação.

Essa integração reduz a necessidade de infraestruturas separadas, mas exige gerenciamento, capacidade adequada e mecanismos de segurança.

### Qualidade de Serviço (QoS)

QoS é o conjunto de mecanismos utilizados para administrar o tráfego da rede conforme as necessidades das aplicações.

Pode utilizar classificação, marcação, filas, priorização, policiamento e modelagem de tráfego.

Aplicações de voz e vídeo interativo são sensíveis à latência e ao jitter, enquanto transferências de arquivos geralmente priorizam integridade e confiabilidade.

## 16.2 Internet das Coisas (IoT)

Internet das Coisas representa a conexão de objetos físicos à rede para coletar informações, compartilhar dados e executar ações.

Uma solução IoT pode possuir:

- Sensores.
- Atuadores.
- Dispositivos de comunicação.
- Gateways.
- Plataformas de processamento.
- Sistemas de armazenamento.
- Interfaces de monitoramento.

### Exemplo de funcionamento

Um sensor monitora a temperatura de um ambiente e envia as informações para um gateway. Os dados são encaminhados para uma plataforma de processamento, que identifica uma condição anormal e pode acionar um sistema de refrigeração.

Os principais desafios incluem segurança, autenticação, privacidade, atualização de firmware, consumo energético e interoperabilidade.

---

# 17. Funcionamento Integrado de uma Comunicação

Para compreender como os diferentes protocolos trabalham em conjunto, considere um computador acessando um servidor remoto por meio de um navegador.

1. O usuário digita o endereço de um site.
2. O navegador solicita ao DNS a resolução do nome de domínio.
3. O DNS retorna o endereço IP associado ao servidor.
4. A aplicação inicia a comunicação utilizando o protocolo de transporte.
5. Se utilizar TCP, ocorre o Three-Way Handshake.
6. O computador consulta sua tabela de rotas para identificar se o destino é local ou remoto.
7. Se o destino for remoto, identifica o gateway padrão.
8. O computador consulta a tabela ARP para descobrir o MAC do gateway.
9. Se necessário, envia um ARP Request e recebe um ARP Reply.
10. O TCP organiza os dados em segmentos.
11. O IP acrescenta os endereços lógicos de origem e destino.
12. A Ethernet cria o quadro utilizando o MAC de origem e o MAC do gateway como destino.
13. O switch encaminha o quadro ao roteador.
14. O roteador remove o quadro, analisa o pacote IP e consulta sua tabela de roteamento.
15. O roteador encaminha o pacote para o próximo salto, criando um novo quadro para o enlace seguinte.
16. O processo se repete até o pacote chegar à rede do servidor.
17. O servidor realiza o desencapsulamento e entrega os dados à aplicação.
18. A resposta percorre o caminho de volta até o computador.

Durante esse processo, os endereços MAC são utilizados em cada enlace e podem mudar a cada roteador. Os endereços IP normalmente permanecem associados à origem e ao destino finais, exceto quando mecanismos como NAT modificam os endereços.

---

# 18. Referências Bibliográficas

## 18.1 Bibliografia básica

- BARRETO, J. S.; ZANIN, A.; SARAIVA, M. O. **Fundamentos de redes de computadores**. Porto Alegre: Sagah, 2018.
- FOROUZAN, B. **Comunicação de dados e redes de computadores**. 4. ed. Porto Alegre: AMGH, 2010.
- TANENBAUM, F. B. et al. **Princípios de comunicação de dados**. Porto Alegre: Sagah, 2021.

## 18.2 Bibliografia complementar

- CARISSIMI, A. S.; ROCHOL, J.; GRANVILLE, L. Z. **Redes de computadores**. Porto Alegre: Bookman, 2009.
- COMER, D. E. **Interligação em redes com TCP/IP**. 6. ed. Editora Campus, 2015.
- CORREA, S. C. S. et al. **Redes de longa distância**. Porto Alegre: Sagah, 2021.
- MORAES, A. F. **Segurança em redes: fundamentos**. São Paulo: Érica, 2010.
- ROCHOL, J. **Comunicação de dados**. Porto Alegre: Bookman, 2012.
- **International Journal of Computer Network and Information Security**. Hong Kong: Modern Education and Computer Science Press, 2009–.

## 18.3 Referências do roteiro de aulas

- YOUNG, Paul H. **Técnicas de comunicação eletrônica**. 5. ed. São Paulo: Pearson Prentice Hall, 2006.
- TANENBAUM, Andrew S.; WETHERALL, David J. **Redes de computadores**. 5. ed. Pearson, 2011.
- KUROSE, James F.; ROSS, Keith W. **Redes de computadores e a Internet: uma abordagem top-down**. 5. ed. São Paulo: Addison Wesley, 2010.

## 18.4 Padrões e documentos técnicos

- IEEE 802.3 — Ethernet.
- IEEE 802.11 — Wireless LAN.
- IEEE 802.1Q — VLAN.
- RFC 791 — IPv4.
- RFC 8200 — IPv6.
- RFC 9293 — TCP.
- RFC 768 — UDP.
- RFC 826 — ARP.
- RFC 1034 e RFC 1035 — DNS.
- RFC 2131 — DHCP.
- RFC 3550 — RTP.

---

## Considerações finais

As redes de computadores dependem da integração entre diferentes tecnologias e protocolos. A camada física transporta os sinais; a camada de enlace organiza a comunicação local; a camada de rede realiza o endereçamento e o encaminhamento; a camada de transporte estabelece a comunicação entre processos; e a camada de aplicação disponibiliza os serviços utilizados pelos usuários.

A compreensão conjunta desses mecanismos permite entender como os dispositivos se comunicam, como os pacotes percorrem diferentes redes e como os serviços da Internet funcionam.

---

**Disciplina:** Comunicação de Dados e Redes de Computadores  
**Curso:** Engenharia de Software  
**Instituição:** UNICEPLAC
