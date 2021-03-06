# QFlask
QFlask creates a wrapper around a flask application and shows it in a QtWebEngineView.

## Requirements
- PyQt5 >= 5.4
- flask (obviously)

## Usage
Adding QFlask to an existing flask project is fairly simple. Instead of calling `run()` on the flask application directly, wrap a `QFlask` instance around it:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello World!'

if __name__ == '__main__':
    from qflask import QFlask
    QFlask(app).run(title='My QFlask App', zoom=2)
```
QFlask takes care of choosing a free port on itself.

### Possible Parameters for `QFlask.run(...)`:
| parameter   | description                                      |
|-------------|--------------------------------------------------|
| `title`     | title of the window                              |
| `icon`      | path to a window icon file                       |
| `width`     | initial width of the window                      |
| `height`    | initial height of the window                     |
| `zoom`      | zoom factor of the web content (defaults to 1)   |
| `**options` | options to be forwarded to the flask application |
