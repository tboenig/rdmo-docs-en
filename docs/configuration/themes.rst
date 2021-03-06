Themes
------

RDMO allows for a high level of customization by modifying the Django *templates* as well as the *static* assets (CSS file, images, etc.). Django, which RDMO is base on, offers a powerful method for this. Inside your ``rdmo-app`` directory, you can create a ``theme`` folder with a ``static`` and a ``templates`` directory inside:

.. code:: python

    mkdir theme theme/static theme/templates

Then add:

.. code:: python

    THEME_DIR = os.path.join(BASE_DIR, 'theme')

to your ``config/settings/local.py``.

Now, templates and static files in the ``theme`` directory are used instead of the original files as long as they have the same relative path, e.g. the template ``theme/templates/core/base_navigation.html`` overrides ``core/templates/core/base_navigation.html`` from the original code.

Usually, the RDMO template files are located in the your virtual environment, e.g. ``/srv/rdmo/rdmo-app/env/lib/python2.7/site-packages/rdmo/core/static/core/css/variables.scss``. The exact path depends on your Python version and platform. We recomended to download the original files from the `rdmo repository <https://github.com/rdmorganiser/rdmo>`_ instead. For the example above, this would be https://github.com/rdmorganiser/rdmo/blob/master/rdmo/core/static/core/css/variables.scss.

Some files you might want to override are:

SASS variables
    https://github.com/rdmorganiser/rdmo/blob/master/rdmo/core/static/core/css/variables.scss can be copied to ``theme/static/css/variables.scss`` and be used to customize colors.

Navigation bar
    https://github.com/rdmorganiser/rdmo/blob/master/rdmo/core/templates/core/base_navigation.html can be copied to ``theme/templates/core/base_navigation.html`` and be used to customize the navbar.

Home page text
    https://github.com/rdmorganiser/rdmo/blob/master/rdmo/core/templates/core/home_text_en.html and https://github.com/rdmorganiser/rdmo/blob/master/rdmo/core/templates/core/home_text_de.html can be copied to ``theme/templates/core/home_text_en.html`` and ``theme/templates/core/home_text_de.html`` and be used to customize text on the home page.

Note that updates to the RDMO package might render your theme incompatible to the RDMO code and cause errors. In this case the files in ``theme`` need to be adjusted to match their RDMO counterparts in functionality.
