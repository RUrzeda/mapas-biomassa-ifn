# Biomassa aérea estimada — Amazônia, Cerrado e Maranhão

Mapa interativo de biomassa aérea (AGB) estimada por um modelo calibrado com
3.657 unidades amostrais do Inventário Florestal Nacional brasileiro e
sensoriamento remoto orbital de acesso livre.

**Página:** https://rurzeda.github.io/mapas-biomassa-ifn/mapa_biomassa.html

## Unidades mapeadas

| Unidade | Resolução | Área | R² contra o IFN | RMSE | Erro mediano |
|---|---|---|---|---|---|
| Maranhão | 100 m | 329.649 km² | 0,165 | 28,5 | 15,7 |
| Cerrado | 250 m | 1.984.546 km² | 0,303 | 32,7 | 14,3 |
| Amazônia | 250 m | 4.215.410 km² | 0,554 | 86,9 | 43,0 |

Métricas em t ha⁻¹, calculadas contra as unidades amostrais do IFN situadas
dentro de cada unidade mapeada.

## Três camadas

- **Biomassa** — AGB estimada, em classes que correspondem aos estratos usados na
  validação, de modo que a cor de uma região possa ser consultada na tabela de
  viés.
- **Incerteza** — amplitude entre os percentis 10 e 90 das 300 árvores do Random
  Forest. É intervalo de referência, não de confiança.
- **Procedência** — quantas das dezoito variáveis preditoras foram imputadas pela
  mediana do bioma em cada pixel. A Amazônia tem 21,8% da área com ao menos uma
  imputação, contra 7,1% no Cerrado e 1,4% no Maranhão; as faixas diagonais
  correspondem a emendas entre órbitas do mosaico ALOS/PALSAR.

## Como ler estes mapas

O viés agregado de cada mapa é próximo de zero, **e isso não indica acurácia**.
Resulta do cancelamento entre superestimação nas faixas de baixa biomassa, que o
modelo infla, e subestimação nas de alta, que ele achata. O viés por classe está
na legenda da própria página, ao lado de cada cor.

Os mapas servem para descrever padrão espacial e para estimativa agregada em área
extensa. Não servem para valor absoluto em pixel nem para contabilidade de carbono
em imóvel ou projeto individual.

## Dados de origem

- **Inventário Florestal Nacional**, Serviço Florestal Brasileiro, disponibilização
  de setembro de 2025. Biomassa calculada pela equação alométrica de Chave et al.
  (2014).
- **Sensoriamento remoto** via Google Earth Engine: Sentinel-2 SR Harmonized,
  Sentinel-1 GRD, mosaico anual ALOS/PALSAR-2, SRTM, ETH Global Canopy Height
  (Lang et al., 2023), Global Short Vegetation Height e GEDI L4A/L2A.
- **Limites territoriais**: IBGE.

O arquivo `limites.json` inclui as coordenadas, a biomassa medida, o ano e o
identificador das 4.219 unidades amostrais do IFN usadas na validação de cada
unidade mapeada. Quem pretenda reutilizar esses pontos deve verificar junto ao
Serviço Florestal Brasileiro as condições de uso do dado de origem.

## Autoria

Roberto de Urzêda Paiva — Laboratório de Processamento de Imagens e
Geoprocessamento (LAPIG), Universidade Federal de Goiás.

Produto da tese de doutorado em andamento. O modelo e a metodologia estão
descritos em manuscrito submetido ao Simpósio Brasileiro de Sensoriamento Remoto
(SBSR 2027).
