# Entendendo o SUMO

Duas informações são necessárias para realizar uma simulação SUMO:

- Uma topologia de rede: é composta de redes, trilhos, calçadas de pedestres, rotas aquáticas e outras tipos de vias. Pode ser criada a partir de um arquivo OSM (OpenStreetMap).

- Um padrão de demanda de tráfego: é composta de carros, ônibus, trams, caminhões, barcos e pedestres movendo pela rede, em um padrão específico.

Essas duas informações fazem parte da configuração, ou `configuration`, que pode ser definida através de um arquivo XML no SUMO.

Vale indicar que o SUMO é uma coleção de programas:

- Programas para rodar uma simulação:
    - **SUMO**: simulador microscópico sem visualização (aplicação CLI).
    - **SUMO-GUI**: simulador microscópico com GUI.

- Programas para criar e manipular a topologia de redes:
    - **NETCONVERT**: responsável por importar e/ou gerar redes; lê redes de diferentes formatos e as converte para o formato SUMO.
    - **NETEDIT**: um editor de redes com interface gráfica.
    - **NETGENERATE**: gera redes abstratas para uma simulação SUMO.

- Programas para definir a demanda de tráfego:

> ***[Observação]*** **Definição de um arquivo OSM:**
>
> OSM files are XML based and typically used to export an extent of the OpenStreetMap GIS service into other applications. An OSM file typically contains geo-referenced descriptions of streets, blocks, parcels and points.

## Rodando uma simulação SUMO

Utilizando OSMWebWizard foi criado uma pasta com todos os dados necessários para uma simulação: um arquivo de configuração `osm.sumocfg` e os arquivos de rotas, de viagens e de topologia da rede. Essa ferramenta cria uma configuração de tráfego determinístico.

Comandos úteis:

```sh
$ python /usr/share/sumo/tools/osmWebWizard.py
```

```sh
$ python /usr/share/sumo/tools/xml/xml2csv.py output/vehicles.fcd --separator ","
```

```sh
$ sumo -c configuration/osm.sumocfg --fcd-output output/vehicles.fcd --fcd-output.geo
```

```sh
$ sumo-gui -c configuration/osm.sumocfg
```