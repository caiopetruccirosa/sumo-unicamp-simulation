Duas informações são necessárias para realizar uma simulação SUMO:

- Uma topologia de rede: é composta de redes, trilhos, calçadas de pedestres, rotas aquáticas e outras tipos de vias.
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
    -

---

Utilizando OSMWebWizard foi criado um arquivo chamado `unicamp_map.osm`.

Definição de um arquivo OSM (OpenStreetMap):

> OSM files are XML based and typically used to export an extent of the OpenStreetMap GIS service into other applications. An OSM file typically contains geo-referenced descriptions of streets, blocks, parcels and points.


Essa ferramenta cria uma configuração de tráfego randomizado

```sh
$ python /usr/share/sumo/tools/osmWebWizard.py
```

```sh
$ python /usr/share/sumo/tools/xml/xml2csv.py output/vehicles.fcd --separator ","
```

```sh
$ python /usr/share/sumo/tools/xml/xml2csv.py output/vehicles.fcd --separator ","
```

```sh
$ sumo -c configuration/osm.sumocfg --fcd-output output/vehicles.fcd --fcd-output.geo
```