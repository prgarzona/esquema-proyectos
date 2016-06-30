# Proyecto de Sphinx para generar documentación del Proyecto

Este es un proyecto básico creado con  [Sphinx](http://www.sphinx-doc.org/en/stable/), para ser utilizado como un esquema del contenido que debe llevar el documento de diseño del proyecto del curso de Análisis y Diseño 2.

## Requerimientos
Existen algunos requerimientos básicos de software necesarios para hacer funcionar de mejor manera el proyecto:

* Python
* Sphinx

Si utiliza Windows o OsX, python es mejor que esté instalado con algún gestor que le permita instalar otras dependencias, como [Anaconda](https://www.continuum.io/downloads) el cual ya incluye sphinx.

Si utiliza linux, solamente es necesario utilizar el gestor de paquetes y buscar python y sphinx

Opcionales:
* Atom con el paquete [language-restructuredtext](https://atom.io/packages/language-restructuredtext)
* LaTeX (para convertir a PDF)

## Configuración
Para utilizar éste proyecto se debe de configurarse algunos archivos para poder crear la documentación adecuadamente:

En el archivo *source/config.py* se debe de cambiar la sección del nombre del documento y del autor:

```python
# General information about the project.
project = u'Documentación de proyecto "Nombre"'
copyright = u'2016, "Alumno"'
```

Recuerde no cambiar la u al inicio de la cadena de texto, ya que ésto le indica a python que es una cadena de texto en codificación utf.

Si va a convertir a PDF es necesario también configurar toda el área de LaTeX:

```python
latex_documents = [
  ('index', 'DocumentacindeproyectoNombre.tex', u'Documentación de proyecto "Nombre" Documentation',
   u'Alumno', 'manual'),
]
# ...
# ...
texinfo_documents = [
  ('index', 'DocumentacindeproyectoNombre', u'Documentación de proyecto "Nombre" Documentation',
   u'Alumno', 'DocumentacindeproyectoNombre', 'One line description of project.',
   'Miscellaneous'),
]
```

## Creación del documento
Use el script **make** para generar el documento con la información que necesite.

En algunas distribuciones de Linux, deberá instalar el comando *make* para que funcione.

```
make html
make latexpdf
```

En windows el comando puede cambiar a **make.md**
