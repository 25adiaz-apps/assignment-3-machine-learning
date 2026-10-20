# Literature review

Material de apoyo para la revisión de literatura.

```
literature-review/
└── metodos/
    ├── metodos.ipynb      Explicación de los métodos que aparecen en los artículos revisados
    └── requirements.txt   Librerías del notebook (numpy, scipy, matplotlib, EMD-signal)
```

## Notebook de métodos

[`metodos/metodos.ipynb`](metodos/metodos.ipynb) organiza los métodos **por función**: cada función es una sección de nivel 1 y cada método una subsección dentro de ella. Al inicio hay una tabla de contenido con todas las funciones y métodos.

| Función | Método |
|---|---|
| 1. Descomposición de señales | 1.1 EMD (Empirical Mode Decomposition) |
| 2. Envolvente de amplitud / amplitud instantánea | 2.1 Transformada de Hilbert |

### Convenciones para agregar un método

- Si el método no encaja en ninguna función existente, se crea una nueva sección de función.
- Se actualiza la tabla de contenido del notebook (y la de este README).
- Cada método incluye, en este orden: **Concepto**, **Descripción del procedimiento**, **Fórmulas** (LaTeX en celdas Markdown; debajo, el significado de cada símbolo y la fórmula en palabras), **Código**, **Gráficas**, **Fortalezas y debilidades** y **Uso en la literatura**.
- Texto explicativo en español; código (variables y comentarios) en inglés, con datos de ejemplo.
- Antes de hacer commit se ejecuta el notebook completo para que las gráficas queden guardadas:

```bash
pip install -r literature-review/metodos/requirements.txt
jupyter nbconvert --to notebook --execute --inplace literature-review/metodos/metodos.ipynb
```
