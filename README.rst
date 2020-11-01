===================================
Django Oscar API for Vue-Storefront
===================================

This package provides a RESTful API for `django-oscar <https://github.com/django-oscar/django-oscar>`_ adapted to `vue-storefront <https://github.com/DivanteLtd/vue-storefront>`_.

Usage
=====

Still under development, no release yet.


Notes
=====

`Documentation <https://github.com/DivanteLtd/storefront-integration-sdk/blob/tutorial/Dynamic%20API%20specification.md>`_ we are following for the api.

`Better definition of required fields <https://github.com/DivanteLtd/bigcommerce2vuestorefront/tree/master/src/templates>`_

`Data Definitions <https://divanteltd.github.io/vue-storefront/guide/data/elasticsearch.html#product-type>`_

Developing
==========

1. To start using ``git clone`` then cd into directory and run ``pip install -e .``

2. Add ``oscar_vue_api`` to INSTALLED_APPS:
::
   INSTALLED_APPS = [
       ....
       'rest_framework',
       'corsheaders',
       'oscar_vue_api',
   ]
   MIDDLEWARE = (
       'corsheaders.middleware.CorsMiddleware',
       #...
   )
   CORS_ORIGIN_ALLOW_ALL = True
   REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': (
        ....
        'oscar_vue_api.authentication.TokenAuthSupportQueryString',
    )
   }

3. Import the api urls to your projects ``urls.py`` file:
::
   urlpatterns = [
       ....
       path('vsbridge/', include('oscar_vue_api.urls')),
   ]


Notes
=====

Export exsisting categories and products to elasticsearch: ``./manage.py oav_export``

Delete all ElasticSearch entries ``curl -X DELETE 'http://localhost:9200/_all'``



