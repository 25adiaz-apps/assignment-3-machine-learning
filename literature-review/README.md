# Literature review

Material de apoyo para la revisión de literatura.

```
literature-review/
└── metodos/
    ├── metodos.ipynb      Explicación de los métodos que aparecen en los artículos revisados
    ├── requirements.txt   Librerías del notebook (numpy, scipy, matplotlib, ipywidgets, EMD-signal)
    └── prompt_explicar_metodos.md   Instrucciones para el chat de Claude: explicar un método y generar el prompt para agregarlo al notebook
```

## Notebook de métodos

[`metodos/metodos.ipynb`](metodos/metodos.ipynb) organiza los métodos **por función**: cada función es una sección de nivel 1 y cada método una subsección dentro de ella. Al inicio hay una tabla de contenido con todas las funciones y métodos.

| Función | Método |
|---|---|
| 1. Descomposición de señales | 1.1 EMD (Empirical Mode Decomposition) |
| 2. Envolvente de amplitud / amplitud instantánea | 2.1 Transformada de Hilbert |

### Flujo para agregar un método

1. En un chat con Claude, pegar las instrucciones de [`metodos/prompt_explicar_metodos.md`](metodos/prompt_explicar_metodos.md) y pedir la explicación del método.
2. Al terminar, Claude entrega un prompt para Claude Code.
3. Ese prompt se le da a Claude Code, que agrega el método al notebook, lo ejecuta y hace commit y push.

### Convenciones para agregar un método

- Si el método no encaja en ninguna función existente, se crea una nueva sección de función.
- Se actualiza la tabla de contenido del notebook (y la de este README).
- Cada método se explica como una **narrativa con orden lógico** (problema → idea central → formulación paso a paso → caso que lo rompe → requisitos previos → aplicación a puentes → síntesis), no en bloques separados: en cada paso van juntas la explicación, la fórmula en LaTeX (con el significado de cada símbolo y la descripción en palabras), el código, la gráfica y su interpretación. El detalle está en [`metodos/prompt_explicar_metodos.md`](metodos/prompt_explicar_metodos.md).
- Los widgets interactivos (`ipywidgets`) van acompañados de una gráfica estática equivalente, porque GitHub no los muestra. Semilla fija para cualquier dato aleatorio.
- Texto explicativo en español; código (variables y comentarios) en inglés, con datos de ejemplo.
- Antes de hacer commit se ejecuta el notebook completo para que las gráficas queden guardadas:

```bash
pip install -r literature-review/metodos/requirements.txt
jupyter nbconvert --to notebook --execute --inplace literature-review/metodos/metodos.ipynb
```
