# Reikjv Stream - BRS Edition

Reikjv Stream - BRS Edition é uma versão personalizada do OBS Studio preparada para operações BRS com vídeo ROV, overlays operacionais, captura, telemetria e ferramentas de apoio em campo. Inclui recursos para UT, CP Probe, organização automática de arquivos e operação de ROV.

O objetivo é entregar um ambiente pronto para uso: instalar, ativar, conectar as fontes necessárias e operar com o layout BRS padrão.

## Download

Baixe a versão mais recente na página oficial de releases:

[Releases do Reikjv Stream - BRS Edition](https://github.com/Reikjv/reikjv-stream/releases)

Arquivo recomendado:

```text
Reikjv Stream - BRS Edition Installer vX.X.X.exe
```
## Requisitos

- Windows 10 ou Windows 11, 64 bits.
- Permissão de administrador para instalar ou atualizar.
- Licença BRS válida para abrir o programa.
- GStreamer 1.0 x64 e Microsoft Visual C++ Redistributable 2015–2022 x64: instalados pelo assistente quando necessário.

## Recursos principais

- Layout padrão BRS com docks organizadas para Captura, Fontes, Controles, ROV, Status Operacional, Legenda, Overlay, UT Probe, CP Probe, Visualização UT/CP e Emulador ROV.
- Overlay Geral nativo configurável em 3, 4 ou 5 colunas e 3 linhas, com perfis salvos, rótulos personalizados e dados em uma ou mais linhas.
- Informações de data/hora, profundidade, azimute, GPS, UTM, Dive Point, embarcação, ROV, UT e CP.
- Legenda com envio manual/automático e tamanhos Compacto (32 px), Padrão (48 px) e Grande (72 px), sem caixa fixa que corte textos longos.
- Receptores NMEA independentes para posição do ROV, heading do ROV, posição da embarcação, heading da embarcação e Dive Point.
- NMEA por UDP ou TCP, com reconexão TCP e suporte a GGA, HDT, HDM e HDG. Quando HDT e HDM existem, o heading verdadeiro tem prioridade.
- Coordenadas em Latitude/Longitude ou N/E UTM, com zona UTM automática ou manual e exibição normal ou compacta.
- Telemetria MAVLink por `mavlink2rest` para profundidade e azimute, consultada em `http://192.168.2.2:6040`.
- Painel ROV com profundidade, tensão, corrente, heading e inclinação.
- UT Probe por rede ou serial, com baud rates de 1200 a 115200; CP Probe por rede.
- Visualização grande de Espessura UT e Potencial CP, além de janelas UT e CP redimensionáveis para o piloto.
- Emulador ROV para profundidade e azimute; reprodução de vídeo QGroundControl com leitura sincronizada de arquivo `.ass` para data, hora, profundidade e azimute.
- Captura manual, automática, anomalia e mosaico; os prints ficam separados dos vídeos.
- Fonte nativa GStreamer para vídeo ROV e presets simplificados para IP Cam.
- Integração com ativador de licença BRS.
- Diagnóstico de encoder disponível após instalação/atualização, sem alterar automaticamente as configurações de gravação.

## Instalação e atualização

1. Baixe o instalador na página de releases.
2. Execute o `.exe` como administrador.
3. Siga o assistente.
4. Ao final:
   - se a licença já existir na máquina, o instalador oferece abrir o Reikjv Stream;
   - se não existir, o instalador oferece abrir o ativador.
5. Após instalar ou atualizar, o programa pode solicitar a verificação dos encoders disponíveis. Essa verificação é informativa; as configurações atuais não são trocadas automaticamente.

Instalação padrão:

```text
C:\Program Files\Reikjv Stream - BRS Edition
```

O instalador detecta versões anteriores e executa atualização preservando:

- licença da máquina;
- configurações existentes;
- pasta de saída;
- vídeos, prints e logs.

Antes de atualizar, feche o Reikjv Stream.

## Organização dos arquivos

Por padrão, o instalador configura:

```text
Vídeos:          Vídeos\Reikjv Stream - Videos
Prints:          Imagens\Reikjv Stream - Prints
Logs:            Documentos\Reikjv Stream - Logs
```

Vídeos e todos os tipos de print são organizados por legenda/atividade. Os logs operacionais são mantidos por semana e por categoria; UT, CP, Overlay e Eventos do Sistema são separados também por dia, por exemplo:

```text
2026-S31\UT\UT_Probe_2026-08-01.csv
2026-S31\CP\CP_Probe_2026-08-01.csv
2026-S31\overlay\overlay_2026-08-01.csv
2026-S31\sistema\eventos_programa_2026-08-01.csv
```

A troca do CSV diário ocorre automaticamente à meia-noite, inclusive se o programa ficar aberto. O `log_gravacoes.csv` é um histórico único com uma linha por vídeo. Todos esses registros utilizam CSV UTF-8 com separador `;` e incluem segundos no horário.

## Overlay Geral

O Overlay Geral permite montar informações operacionais em uma grade simples:

- 3, 4 ou 5 colunas;
- 3 linhas;
- tamanho de fonte configurável;
- rótulos customizáveis;
- perfis de overlay;
- dados NMEA independentes por função.

Para coordenadas UTM, a zona pode ser:

- `Automática`: calculada pela longitude recebida no NMEA;
- `Manual`: definida pelo operador, útil quando o projeto ou emulador trabalha com uma zona fixa.

## Telemetria

### NMEA

Ao escolher uma célula NMEA no Overlay, o receptor correspondente é exibido para configuração. Cada função pode ter seu próprio protocolo, endereço e porta. Após 10 segundos sem dados, o último valor é preservado em cinza para sinalizar informação congelada.

### MAVLink

Profundidade e Azimute (MAVLink) usam a API `GLOBAL_POSITION_INT` do `mavlink2rest`:

```text
http://192.168.2.2:6040/mavlink/vehicles/1/components/1/messages/GLOBAL_POSITION_INT
```

O Emulador ROV e a reprodução QGroundControl só substituem esses valores enquanto estiverem habilitados. Para utilizar a telemetria real, mantenha essas opções desmarcadas.

## Ativação

O programa requer uma licença BRS válida. Caso a máquina ainda não esteja ativada, o Reikjv Stream mostra o fingerprint da máquina e oferece abrir o ativador.

> A licença é validada ao iniciar o programa. O instalador apenas identifica se já existe uma licença na máquina.

## Notas de segurança do Windows

Algumas versões podem apresentar alerta do Windows SmartScreen ou antivírus por não possuírem assinatura Authenticode pública.

Baixe o instalador somente pela página oficial de releases do repositório usado pela BRS/Reikjv.

## Créditos

Baseado no [OBS Studio](https://obsproject.com/), projeto open source mantido pela comunidade OBS, com personalizações para operações BRS/Reikjv.
