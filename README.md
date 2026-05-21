# Edicio de video multicàmera
Notebook amb el qual s'ha elaborat model capaç de suggerir quin és el punt de vista més indicat a mostrar en un entorn multicàmera.

## Instal·lació

El codi presentat s'ha elaborat amb les següents llibreries:

|Llibreria  |Versió  |Descripció                                     |
|-----------|--------|-----------------------------------------------|
|Pytorch    |2.11    |Llibreria de Deep Learning amb suport per a GPU.|
|Timm       |1.0.27  |Col·lecció de codi obert que inclou models pre-entrenats de deep-learning.|
|torchvision|0.26.0  |Conjunts de datasets populars, models i conjunt d'operacions d'imatge en deep learning.|
|matplotlib |3.10.9  |Llibreria per crear visualitzacions en Python.|
|numpy      |2.4.4   |CLlibreria de python per treballar amb arrays.|
|seaborn    |0.13.2  |Llibreria construïda sobre matplotlib que simplifica la creació de gràfics avançats.|


En el repositori s'inclou un entorn amb les depndències necessàries per crear-ne el model amb aquest notebook.

``
pip install -r requirements.txt
``

## Estructura

El repositori inclou:

|artxiu|Descripció|
|------|----------|
|main.ipynb| Codi amb el que s'ha entrenat el model|
|main.html| Versió en html del jupyter notebook|
