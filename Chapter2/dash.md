# Dash

Dash é uma biblioteca de interface web para usuários com foco para análise, exploração e reporte de dados;

- Todos os elementos no Dash são customizáveis (tamanho, cor e posicionamento) ;

- Não possui necessidade de saber escrever códigos HTML ou Javascript, apenas Python*;

**Arquitetura**

Aplicações Dash são web servers baseados em Flask com comunicação por JSONs através de requisições HTTP.

Confira mais detalhes neste [artigo](https://medium.com/plotly/introducing-dash-5ecf7191b503).


## Instalação e Uso

Recomendo o uso do Dash com uma [virtualenv](https://docs.python.org/pt-br/3/library/venv.html). 

Em geral, o processo de uso pode ser:


```
python3 -m venv venv-dash
source venv-dash/bin/activate
pip install -r requirements.txt
```

Onde a primeira linha cria a virtualenv, a segunda ativa e a terceira instala os pacotes necessarios. Para sair, pode ser usado na linha de comando `deactivate`. 

## Dash Layouts

Confira esta página da [documentação](https://dash.plotly.com/layout).

## Dash Core Components

Confira esta página da [documentação](https://dash.plotly.com/dash-core-components)

O Dash Core Components fornece uma coleção de componentes de interface do usuário interativos e personalizáveis que podem ser usados para criar painéis dinâmicos e responsivos. Alguns dos principais componentes são:

- Gráfico: este componente permite a criação de vários tipos de tabelas e gráficos interativos, como gráficos de linhas, gráficos de barras, gráficos de dispersão e muito mais. Ele oferece amplas opções de personalização, incluindo cores, rótulos e dicas de ferramentas. Neste componente iremos adicionar gráficos do Plotly.

- Dropdown: este componente cria um menu suspenso que permite aos usuários selecionar uma ou várias opções de uma lista. Ele pode ser usado para filtragem dinâmica, seleção de dados ou qualquer outro recurso interativo que dependa da entrada do usuário.

- Slider: o Slider permite que os usuários selecionem um valor ou um intervalo deslizando uma alça ao longo de uma trilha. Ele pode ser usado para filtrar dados, definir parâmetros numéricos ou controlar outros componentes dinamicamente.

- Entrada (Input): o componente Entrada fornece um campo de entrada que permite aos usuários inserir valores de texto ou numéricos. Ele pode ser usado para funcionalidade de pesquisa, entrada de dados ou qualquer outro requisito de entrada interativa.

- DatePicker: o componente DatePicker exibe uma interface de calendário e permite que os usuários selecionem uma data ou um intervalo de datas. É útil para filtrar dados com base em períodos de tempo específicos.

- DataTable: o componente DataTable renderiza dados tabulares com recursos como classificação, filtragem, paginação e seleção de linha. Ele fornece uma maneira interativa de exibir e manipular dados estruturados.

## Dash Callbacks

As callbacks são um recurso fundamental no framework Dash, que permitem atualizar dinamicamente os componentes de uma aplicação web com base em eventos ou interações do usuário. As callbacks no Dash são definidas usando a anotação `@app.callback` e permitem que os desenvolvedores especifiquem as entradas, as saídas e as funções que serão executadas quando ocorrerem alterações nas entradas.

Confira na documentação a estrutura das callbacks:

- [Callbacks básicas](https://dash.plotly.com/basic-callbacks)
- [Callbacks avançadas](https://dash.plotly.com/advanced-callbacks)


## Templates

Um template geral para um app Dash pode ser visto a seguir:

```
import dash
import dash_core_components as dcc
import dash_html_components as html

# Create the Dash app
app = dash.Dash(__name__)

# Define the layout
app.layout = html.Div(
    children=[
        html.H1("My Dash App"),
        dcc.Graph(
            id="example-graph",
            figure={
                "data": [
                    {"x": [1, 2, 3], "y": [4, 1, 2], "type": "bar", "name": "Data 1"},
                    {"x": [1, 2, 3], "y": [2, 4, 5], "type": "bar", "name": "Data 2"},
                ],
                "layout": {"title": "Graph Title"},
            },
        ),
    ]
)

# Run the app
if __name__ == "__main__":
    app.run_server(debug=True)
```

Para um repositorio dentro do VS code (ou outra IDE), recomendo o template:

```
├── assets
│   └── style.css
├── components
│   ├── app_callbacks.py
│   ├── graphs.py
│   └── utils.py
└── data
    ├── logs.csv
    ├── new_data2.csv
    └── your_data1.csv
├── app.py
```

### Referência e tutoriais

- [Jupyter Dash Oficial Repo](https://github.com/plotly/jupyter-dash)
- [Estrutura de Aplicacao](https://dash.plotly.com/dash-enterprise/application-structure)
- [Interactive Dashboards and Data Apps with Plotly and Dash](https://github.com/PacktPublishing/Interactive-Dashboards-and-Data-Apps-with-Plotly-and-Dash)
