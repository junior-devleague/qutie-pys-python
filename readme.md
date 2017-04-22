---
author:
- gitten
title: Qutie Pies
type: Activity
---

Summary
=======

An introduction activity for PyQt5, a python library for the
cross-platform application framework Qt. Qt is often used for
applications with graphical user interfaces. This activity provides an
introduction to tools for building the GUI for the GOL project.

Objective
=========

Hey, Hey! We get to play around with graphics in Python! Get comfortable
with displaying simple shapes in a desktop window, then start to build a
prototype of how you would like your GOL project to look.

Prerequisites
=============

-   Basic usage of Python REPL
-   Basic understanding of general Python concepts

Requirements
============

-   shell terminal or Python IDE
-   PyQt5, a Qt library for Python

Desired Outcomes
================

-   Build an intuition about MVC design
-   Basic understanding of using PyQt5 for graphics
-   Increase comfort level of utilizing the REPL for development
-   learn tools for completing Conway's Game of Life project

Tasks
=====

Preparing the activity
----------------------

### From the terminal

1.  Ensure PyQt5 is installed

    ``` {.bash}
    sudo apt install python3-pyqt5
    ```

2.  Create a scratch.py file in a new directory with your text editor.
    In the new file add required modules and setup as shown below

    ``` {.python}
    # in your scratch.py file
    import sys
    from PyQt5.Qtwidgets import (QApplication,
                                 QGraphicsScene,
                                 QGraphicsView,
                                 QGraphicsRectItem)

    from PyQt5.QtGui import QBrush
    from PyQt5.Qt.Core import Qt


    # initial window setup
    app = QApplication(sys.argv)
    Scene = QGraphicsScene(0, 0, 300, 300)
    View = QGraphicsView(Scene)
    ```

3.  start your REPL, set, Go!

    ``` {.bash}
    Python3 -i scratch.py
    ```

Activity
--------

### Testing the waters with the REPL, PyQt5 and cute rectangles!

-   First lets instantiate a rectangle object from our REPL. we can use
    the class `QGraphicsRectItem`.

    ``` {.python}
    #example
    x = 0; y = 0; width = 300; height = 200;
    cute_rectangle = QGraphicsRectItem(x, y, width, height)
    ```

-   In order for the rectangle to be visible, we need to add it to the
    `scene` and signal the `view` to show it. We can use
    `scene.addItem()` and `view.show()` for this.

    ``` {.python}
    scene.addItem(cute_rectangle)
    view.show()
    ```

-   Cuteangle! Now that shape is visible, we can modify the rectangle
    object directly and we should see it update. lets change the color
    using the QBrush class. We can use built-in named colors to make
    things simple too.

    ``` {.python}
    magenta = QBrush(Qt.magenta)
    cute_rectangle.setBrush(magenta)
    ```

-   Yes, so cute! Here is the full list of available named colors.

    -   Qt.white, Qt.black, Qt.red, Qt.darkRed, Qt.green, Qt.darkGreen,
        Qt.blue, Qt.darkBlue, Qt.cyan, Qt.darkCyan, Qt.magenta,
        Qt.darkMagenta, Qt.yellow, Qt.darkYellow, Qt.gray, Qt.darkGray,
        Qt.lightGray, Qt.transparent

-   We can do more than just change the color, try some of the following
    methods to see what they do.

    -   .setRect(x, y, width, height)

    -   .isVisible()

    -   .setVisible(Bool)

    -   .setOpacity(Float)

    -   .setPos(x, y)

    -   .setRotation(Float)

    -   .setX(Float)

    -   .setY(Float)

-   Add some more rectangles and get comfortable with creating them.

### Make GOL cute again

-   Your Main Task today is to start to develop your front-end for the
    GOL project. Create the graphics for the 3 by 3 cell game world to
    start off.

-   To makes things easier, you can create a custom class for your
    default cells. An Example:

    ``` {.python}
    class MyRect(QGraphicsRectItem):
        def __init__(self):
            super().__init__()
            self.set()

        def set(self, x=0, y=0, width=300, height=100):
            self.setRect(x, y, width, height)
            self.setBrush(Qt.cyan)
    ```

### Stretchy Stretch Goal

Make lots of cells! How many can you make? Can you write some cute code
in a few lines?

### Stretchier Stretch Goal

Make the number of cells variable!

### Chewy Stretchy Stretch Goal

If you are ready for this, lets explore the documentation and figure out
mouse events!
