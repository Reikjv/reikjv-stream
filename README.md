# Reikjv Stream - BRS Edition

Reikjv Stream - BRS Edition é uma versão personalizada do OBS Studio preparada para operações BRS com vídeo ROV, overlays operacionais, captura, telemetria e ferramentas de apoio em campo.

O objetivo é entregar um ambiente pronto para uso: instalar, ativar, conectar as fontes necessárias e operar com o layout BRS padrão.

## Download

Baixe sempre a versão mais recente pela página de releases:

[Releases do Reikjv Stream - BRS Edition](https://github.com/Reikjv/reikjv-stream/releases)

Arquivo recomendado para instalação:

```text
Reikjv Stream - BRS Edition Installer vX.X.X.exe
```

## Requisitos

- Windows 10 ou Windows 11 64-bit.
- Permissão de administrador para instalar.
- GStreamer 1.0 x64, instalado automaticamente quando necessário.
- Microsoft Visual C++ Redistributable 2015-2022 x64, instalado automaticamente quando necessário.
- Licença/ativação BRS válida para abrir o programa.

## Principais recursos

- Layout padrão BRS com docks organizadas para operação.
- Overlay Geral nativo com grade configurável de 3, 4 ou 5 colunas.
- Overlay com data, hora, profundidade, azimute, CP, UT, GPS/NMEA e Dive Point.
- Receptores NMEA separados para ROV, embarcação e Dive Point.
- Suporte NMEA por UDP ou TCP.
- Coordenadas em Lat/Lon ou N/E UTM.
- Zona UTM automática ou manual, com exibição normal ou compacta.
- Log simples do overlay a cada segundo com os dados ativos.
- Fonte nativa GStreamer para vídeo ROV.
- Presets simplificados para IP Cam.
- Docks BRS para captura, status operacional, ROV, CP Probe, UT Probe, legenda e controles.
- Integração com ativador de licença BRS.
- Instalador com detecção de atualização e preservação de licença/configurações.

## Instalação

1. Baixe o instalador pela página de releases.
2. Execute o `.exe` como administrador.
3. Siga o assistente de instalação.
4. Ao final:
   - se a licença já existir na máquina, o instalador oferece abrir o Reikjv Stream;
   - se não existir, o instalador oferece abrir o ativador.

Por padrão, o programa é instalado em:

```text
C:\Reikjv Stream - BRS Edition
```

## Atualização

O instalador detecta versões antigas instaladas no caminho padrão e executa atualização preservando:

- licença da máquina;
- configurações existentes;
- pasta de saída;
- vídeos e logs.

Antes de atualizar, feche o Reikjv Stream se ele estiver aberto.

## Ativação

O programa requer uma licença válida para iniciar.

Se a máquina ainda não estiver ativada, o Reikjv Stream exibe o fingerprint da máquina e oferece abrir o ativador.

> A licença é validada ao iniciar o programa. O instalador apenas ajuda a identificar se já existe uma licença na máquina.

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
- `Manual`: definida pelo operador, útil quando o projeto/emulador trabalha com uma zona fixa.

## Notas de segurança do Windows

Algumas versões podem exibir alerta do Windows SmartScreen ou antivírus por ainda não possuírem assinatura Authenticode pública.

Baixe o instalador apenas pela página oficial de releases do repositório usado pela BRS/Reikjv.

## Créditos

Baseado no OBS Studio, com personalizações para operação BRS/Reikjv.

OBS Studio é um projeto open source mantido pela comunidade OBS.

