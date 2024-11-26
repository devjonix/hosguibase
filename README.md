# Hosguibase - An UI toolkit

Hosguibase is an open-source Python toolkit for making graphical
user interfaces. It uses other toolkits as its backends,
creating a uniform, tkinter-like API from the developer's perspective.
This uniformity allows
changing the look and the feel of the program with little to no effort.

Feature wise, hosguibase does not aim to expose many
features from its backends. On the contrary, we look for a
minimal feature set that can be used to create acceptable applications.
This minimalism is to ease the workload needed to
maintain multiple backends.

Hosguibase is developed by DEV Joni since 2023.

Currently, the project is in an early stage not recommended
for production.


## Installing

```
pip install devjoni-hosguibase
```

## API Overview

### Widgets

- MainWindow - The main window
- FrameWidget - Containment and partitioning
- TextWidget - Non-editable text (label)
- ButtonWidget - Clickable -> command
- SliderWidget - Slidable (scale)
- EntryWidget - Single-line editable text
- EditorWidget - Multiline editable text
- DropdownWidget - Selection (optionmenu)
- ImageWidget - Shows an image

The hosguibase API is tkinter like. When creating a new widget,
you specify its parent and then make the widget appear
on the screen by using the grid method.

### A hello world example

```python
import devjoni.guibase as gb

app = gb.MainWindow()
app.title = "My graphical program"
app.geometry = "small"

hello = gb.TextWidget(app)
hello.grid(row=0, column=0)

hello.set(text='Hello world!')

app.run()
```

## Supported Backends

- tkinter : The GUI toolkit based on tcl/tk that comes with Python
- gtk3/4 (via gi): A toolkit used for example by GNOME
- p3d : Panda3D - The open-source 3D rendering engine

The backend is currently selected with flags to the program. The default backend if no other flag is given is GTK3.

Tkinter backend

```
python myprogram.py --tk
```

GTK3 backend

```
python myprogram.py --gtk3
```

GTK4 backend

```
python myprogram.py --gtk4
```

Panda3D backend

```
python myprogram.py --p3d
```


## Current Limitations

- Only gridding supported (no free placement of widgets)
- Playing videos or 3D graphics not straighforward
- No dedicated touch or joystick support


## Contributing

### Reporting Issues

Please feel free to report any bugs or issues in our bug tracker in Github:

[https://github.com/devjonix/hosguibase/issues](https://github.com/devjonix/hosguibase/issues)

### Pull Requests

Despite commercial backing this is a true open-source project.
We appriciate any inputs to the projects.
