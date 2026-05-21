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

També es requereix una copia del TVMCE dataset o un altre conjunt de dades estructurat de la mateixa forma, en concreat cada mostra ha de tenir els camps següents:

- Un Json amb les mostres d'entrenament i altre amb les de test, cada mostra deu tenir la següent estructura:
    + _boundary_: Si' s'ha considerat realitzar un canvi de càmera (0) o no (1).
    + _videoID_: Id del video al que pertany la mostra.
    + _CAMFrame_: Id del fotograma candidat.
    + _outputList_: Fotogrames anteriors al candidat.
    + _currentCam_: Id de la càmera que s'ha utilitzat en els fotogrames anteriors.
    + _CAMList_: Id de les càmeres a les que pertany cada candidat.
    + _selectCAM_: El Id de la càmera a la que pertany el fotograma candidat que finalment es va considerar.

Un directori per als vídeos del conjunt d'entrenament, i un altre amb el de test, que segueixi la següent estructura:

├── train /test                 # Video frames file with a sampling stride of 5 frames
│   │   ├── video_0002         # Video TV Show id
│   │   │   ├── output         # Video frames from the final output
│   │   │   │   ├── 18362.jpg
│   │   │   │   ├── ...
│   │   │   ├── CAM1           # Video frames from different track
│   │   │   │   ├── 18460.jpg
│   │   │   │   ├── ...
│   │   │   ├── CAM2
│   │   │   │   ├── 18460.jpg
│   │   │   │   ├── ...

Finalment, les id de cada frame hauran de reflectir la distància temporal entre fotogrames.

├── DATASET
│   ├── meta
│   │   ├── train.json         
│   │   ├── test.json          
│   ├── train                  
│   │   ├── video_0002         
│   │   │   ├── output         
│   │   │   │   ├── 18362.jpg
│   │   │   │   ├── ...
│   │   │   ├── CAM1           
│   │   │   │   ├── 18460.jpg
│   │   │   │   ├── ...
│   │   │   ├── CAM2
│   │   │   │   ├── 18460.jpg
│   │   │   │   ├── ...
│   │   │   ├── ...
│   │   ├── video_0003         
│   │   │   ├── ...  
│   │   ├── ...
│   ├── test                   
│   │   ├── video_0000
│   │   ├── ...

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
