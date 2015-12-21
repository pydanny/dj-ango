=============================
dj-ango
=============================

.. image:: https://badge.fury.io/py/dj-ango.png
    :target: https://badge.fury.io/py/dj-ango

.. image:: https://travis-ci.org/pydanny/dj-ango.png?branch=master
    :target: https://travis-ci.org/pydanny/dj-ango

Simplifying the import structure of Django.

Documentation
-------------

The full documentation is at https://dj-ango.readthedocs.org.

Quickstart
----------

Install dj-ango::

    pip install dj-ango

Then use it in a project:

.. code-block:: python

    from ango import settings, TemplateView, url

    class AboutView(TemplateView):
        template_name = "about.html"

        def get_context_data(self, **kwargs):
            context = super(AboutView, self).get_context_data(**kwargs)
            context['is_debug_mode'] = settings.DEBUG
            return context

    urlpatterns = [
        url(
            regex=r'^about/$',
            view=AboutView.as_view(),
            name='about'
        )
    ]



Running Tests
--------------

Does the code actually work?

::

    source <YOURVIRTUALENV>/bin/activate
    (myenv) $ pip install -r requirements-text.txt
    (myenv) $ python runtests.py

Credits
---------

Tools used in rendering this package:

*  Cookiecutter_
*  `cookiecutter-pypackage`_

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`cookiecutter-pypackage`: https://github.com/pydanny/cookiecutter-djangopackage
