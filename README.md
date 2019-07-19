### flask-assets
---
https://github.com/miracle2k/flask-assets

```py
from flask import Flask
from flask_assets import Environment, Bundle

app = Flask(__name__)
assets = Environment(app)

js = Bundle('jquery.js', 'base.js', 'widgets.js',
  filters='jsmin', output='gen/packed.js')
assets.register('js_all', js)

app = Flask(__name__)
assets = flask_assets.Environment()
assets.init_app(app)

js = Bundle('app_level.js', 'blueprint/blueprint_level.js')

assets_env.debug = True
app.config['ASSETS_DEBUG'] = True

app.config['FLASK_ASSETS_USE_S3']=True

app.config['FLASK_ASSETS_USE_CDN']=True

entry_points={
  'flask.commands': [
    'assets = flask_assets:assets',
  ],
},

from flask_assets import ManagerAssets
manager = Manager(app)
manager.add_command("assets", ManageAssets(assets_env))

environment.config['sass_bin'] = '/opt/sass/bin/sass'
```

```sh
easy_install Flask-Assets
pip install Flask-Assets

flask --help
```

```
{% assets "js_all" %}
  <script type="text/javascript" src="{{ ASSET_URL }}"></script>
{% endassets %}


{% assets filters="jsmin", output="gen/packed.js",
    "common/jquery.js", "site/base.js", "site/widgets.js" %}
  <script type="text/javascript" src="{{ ASSET_URL }}"></script>
{% endassets %}

```


