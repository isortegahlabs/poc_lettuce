# POC LETTUCE

### Descripción

[Lettuce](http://lettuce.it/tutorial/simple.html#tutorial-simple) es una herramienta que nos permite implementar 
BDD (Behavior Driven Development). Puede ejecutar archivos en formato de texto plano
que contengan pruebas automáticas descritas en forma funcional para proyectos de Python, tal como lo hace Cucumber en Java
o Ruby.

Esto ocasiona que el proceso de desarrollo y pruebas sea realmente fácil, escalable, legible y, lo que es mejor, 
le permite a alguien que no programa describir el comportamiento de un determinado sistema, sin imaginar que esas 
descripciones probarán automáticamente el sistema durante su desarrollo.  
  

![Workflow](imgs/flow.png)

### Requerimientos

* python <= 2.7.0
* virtualenv >= 15.1.0 

** La ultima versión de lettuce solo funciona con Python 2.7

### Instalación

Se recomienda usar un ambiente virtual de python, para lo cual se requiere crearlo de la siguiente forma
por ejemplo:

```bash
user@machine:~$ virtualenv poc_lettuce --python=python2.7
user@machine:~$ source poc_lettuce/bin/activate
```

Una vez se tenga activo el ambiente virtual, instalar lettuce vía pip:
```bash
(poc_lettuce) user@machine:~$ pip install lettuce
```

### Ejecución

Al clonar este proyecto, se encontrarán con la siguiente estructura de proyecto.
```bash
.
├── imgs
│   └── flow.png
├── README.md
└── tests
    └── features
        ├── first.feature
        └── steps.py
```

Para realizar la ejecución solo hay que ejecutar:
```bash
(poc_lettuce) user@machine:~$ lettuce tests/  

Feature: Compute factorial       # tests/features/first.feature:1
  In order to play with Lettuce  # tests/features/first.feature:2
  As beginners                   # tests/features/first.feature:3
  We'll implement factorial      # tests/features/first.feature:4

  Scenario: Factorial of 0       # tests/features/first.feature:6
    Given I have the number 0    # tests/features/steps.py:4
    When I compute its factorial # tests/features/steps.py:8
    Then I see the number 1      # tests/features/steps.py:12

  Scenario: Factorial of 1       # tests/features/first.feature:11
    Given I have the number 1    # tests/features/steps.py:4
    When I compute its factorial # tests/features/steps.py:8
    Then I see the number 1      # tests/features/steps.py:12

  Scenario: Factorial of 2       # tests/features/first.feature:16
    Given I have the number 2    # tests/features/steps.py:4
    When I compute its factorial # tests/features/steps.py:8
    Then I see the number 2      # tests/features/steps.py:12

1 feature (1 passed)
3 scenarios (3 passed)
9 steps (9 passed)
```
