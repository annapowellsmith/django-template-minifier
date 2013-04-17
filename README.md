django-template-minifier
========================


Django package, providing simple template loader. It reduces HTML output in templates by stripping out whitespace characters between HTML and django template tags.


Package Installation
========================


* pip install django-template-minifier
* [download package](https://github.com/), unzip and run python ./setup.py install
* copy template_minifier directory to Your **PYTHONPATH**


Basic usage
========================


Modify Your Django project settings's module:

TEMPLATE_LOADERS = (('django.template.loaders.cached.Loader', (
        'template_minifier.template.loaders.filesystem.Loader',
        'template_minifier.template.loaders.app_directories.Loader',
    )),
)

Be happy having no more spaces and new lines in Your templates!


Advanced usage:
========================


Using modified settings You can:
* turn off stripping spaces between HTML tags
	TEMPLATE_MINIFIER_HTML_TAGS = False; default = True
* turn off stripping spaces between Django template tags (\s{%, %}\s)
    TEMPLATE_MINIFER_TEMPLATE_TAGS = False; default = True
* turn off all stripping
    TEMPLATE_MINIFER = False; default = True
* run Your own strip_function, which preprocess templates
    TEMPLATE_MINIFER_STRIP_FUNCTION = ; default = template_minifier.

Using only in production - just paste this into Your Django project settings's module:

if DEBUG:
    TEMPLATE_MINIFER = False