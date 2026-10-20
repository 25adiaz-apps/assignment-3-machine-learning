# Repositorio de estudio

Repositorio universal de estudio: trabajos de las materias del posgrado y notas de la revisión de literatura.

## Estructura

Cada materia tiene su propia carpeta (nombre de la materia en inglés) y, dentro, una carpeta por cada trabajo.

```
machine-learning/                 Machine Learning for Engineers (CIVE 779)
└── assignment-3/                 Assignment 3: bias/varianza, validación cruzada, SVM
structural-reliability/           Confiabilidad estructural
├── mini-project-2/               Confiabilidad de un tirante de puente atirantado (Monte Carlo)
└── open-question/                Aproximación de primer orden de la tensión de un tirante
requirements.txt                  Librerías generales para correr los notebooks
```

### Trabajos

| Materia | Trabajo | Notebook |
|---|---|---|
| Machine Learning | Assignment 3 | [CIVE779MachineLearningforEngineers-Assignment3.ipynb](machine-learning/assignment-3/CIVE779MachineLearningforEngineers-Assignment3.ipynb) |
| Structural Reliability | Mini-project 2 | [mini_project_2_cable_reliability.ipynb](structural-reliability/mini-project-2/mini_project_2_cable_reliability.ipynb) |
| Structural Reliability | Open question | [open_question_cable_tension.ipynb](structural-reliability/open-question/open_question_cable_tension.ipynb) |

### Cómo agregar contenido nuevo

- **Nuevo trabajo de una materia existente:** crear `<materia>/<trabajo>/` (p. ej. `machine-learning/assignment-4/`).
- **Nueva materia:** crear `<nombre-de-la-materia-en-ingles>/` con una carpeta por trabajo.
- Nombres de carpetas en minúsculas y con guiones.
- Si un trabajo necesita librerías extra, agregar un `requirements.txt` dentro de su carpeta.

## Puesta en marcha

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab                      # o abre los .ipynb en VS Code
```
