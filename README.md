# Teste backend (maps)

Utilizando NodeJS (com ou sem framework, o que achar necessário) junto com Mysql ou Sqlite, crie os seguintes endpoints:

------------------------------------------------------------------------------------------------------------------------

## Obrigatório
```Cadastrar```
Cadastro simples de usuário com email e senha.

```Login```
Autenticação via JSON utilizando e-mail e senha. O sistema deverá retornar alguns dados do usuário junto com um token `jwt`.

```Buscar dados do usuário```
Um endpoint autenticado para buscar os dados do usuário autenticado. A autenticação deverá ser feita com o token `jwt` retornado pela autenticação.

```Verificar se um ponto está dentro de um polígno```

Dado um conjunto de coordenadas que desenha um polígno (em geocoordenadas), implementar um algoritmo de ray-casting para criar uma função que informa se um determinado ponto se encontra dentro ou fora desse polígno. Com base nisso, crie um endpoint que irá receber informações em JSON como latitude e longitude e irá retornar se essa coordenada está dentro ou fora do polígno. 


Referência:
https://geojson.io/#map=13.89/-19.99255/-47.88975

Coordenadas do polígno (você consegue usar esse JSON para renderizar o polígno no mapa enviado acima):
GEOJSON do polígno:
```json

{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {},
      "geometry": {
        "coordinates": [
          [
            [
              -47.87893310332299,
              -19.999396037158164
            ],
            [
              -47.880277060034416,
              -19.989379419023322
            ],
            [
              -47.88630176443493,
              -19.984806426972057
            ],
            [
              -47.88593100392825,
              -19.984153180994568
            ],
            [
              -47.88922128627851,
              -19.981670840607364
            ],
            [
              -47.894272873504065,
              -19.98633078015716
            ],
            [
              -47.89339234130529,
              -19.987071173506493
            ],
            [
              -47.894690061018196,
              -19.988159948864364
            ],
            [
              -47.891584956090014,
              -19.99064242528955
            ],
            [
              -47.89214110428503,
              -19.991208593182606
            ],
            [
              -47.88115757228081,
              -20.001486485815988
            ],
            [
              -47.87990629078212,
              -20.001007415557268
            ],
            [
              -47.87893310332299,
              -19.999396037158164
            ]
          ]
        ],
        "type": "Polygon"
      }
    }
  ]
}
```

Lista de coordenadas para teste:

Coordenadas dentro do polígno:
```javascript
[
{
latitude:  -47.88363636043164,
longitude: -19.988600115962882
},
{
latitude:  -47.889821650898625,
longitude: -19.984874510135086
}
]
```


Coordenadas fora do polígno:
```javascript
[
{
latitude:  -47.881762762375445,
longitude: -19.98626735095681
},
{
latitude:  -47.890747959923544,
longitude: -19.99658269490159
}
]
```





## Bonus

```Endpoint de alerta```
Toda vez que uma coordenada é registrada fora do polígno (durante consulta no endpoint de ray-casting), gerar um registro de alerta com datahora e coordenadas e retornar todos os alertas quando for consultar esse endpoint.

```Logout```
Endpoint consumido por um usuário autenticado para deslogar e adicionar o `jwt` na blacklist (proibir futuras requisições autenticadas com o token de usuário)


------------------------------------------------------------------------------------------------------------------------

# Entrega
- Gravar um vídeo de até 5 minutos mostrando a API em funcionamento:
    - Sugestão: Loom
- Compartilhar código fonte no github ou gitlab para code review e feedback
