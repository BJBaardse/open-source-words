Django REST framework ![build-status-image] ![coverage-status-image] ![pypi-version] Awesome web-browsable Web APIs. Full documentation for the project is available at http://www.django-rest-framework.org. Funding REST framework is a collaboratively funded project. If you use REST framework commercially we strongly encourage you to invest in its continued development by signing up for a paid plan. The initial aim is to provide a single full-time position on REST framework. Every single sign-up makes a significant impact towards making that possible. Many thanks to all our wonderful sponsors, and in particular to our premium backers, Rover, Sentry, Stream, Machinalis, Rollbar, and Cadre. Overview Django REST framework is a powerful and flexible toolkit for building Web APIs. Some reasons you might want to use REST framework: The Web browsable API is a huge usability win for your developers. Authentication policies including optional packages for OAuth1a and OAuth2. Serialization that supports both ORM and non-ORM data sources. Customizable all the way down - just use regular function-based views if you dont need the more powerful features. Extensive documentation, and great community support. There is a live example API for testing purposes, available here. Below: Screenshot from the browsable API Requirements Python (2.7, 3.4, 3.5, 3.6) Django (1.11, 2.0) Installation Install using pip... pip install djangorestframework Add rest_framework to your INSTALLED_APPS setting. INSTALLED_APPS = ( ... rest_framework, ) Example Lets take a look at a quick example of using REST framework to build a simple model-backed API for accessing users and groups. Startup up a new project like so... pip install django pip install djangorestframework django-admin.py startproject example . ./manage.py migrate ./manage.py createsuperuser Now edit the example/urls.py module in your project: ```python from django.conf.urls import url, include from django.contrib.auth.models import User from rest_framework import serializers, viewsets, routers Serializers define the API representation. class UserSerializer(serializers.HyperlinkedModelSerializer): class Meta: model = User fields = (url, username, email, is_staff) ViewSets define the view behavior. class UserViewSet(viewsets.ModelViewSet): queryset = User.objects.all() serializer_class = UserSerializer Routers provide a way of automatically determining the URL conf. router = routers.DefaultRouter() router.register(rusers, UserViewSet) Wire up our API using automatic URL routing. Additionally, we include login URLs for the browsable API. urlpatterns = [ url(r^, include(router.urls)), url(r^api-auth/, include(rest_framework.urls, namespace=rest_framework)) ] ``` Wed also like to configure a couple of settings for our API. Add the following to your settings.py module: ```python INSTALLED_APPS = ( ... # Make sure to include the default installed apps here. rest_framework, ) REST_FRAMEWORK = { # Use Djangos standard django.contrib.auth permissions, # or allow read-only access for unauthenticated users. DEFAULT_PERMISSION_CLASSES: [ rest_framework.permissions.DjangoModelPermissionsOrAnonReadOnly ] } ``` Thats it, were done! ./manage.py runserver You can now open the API in your browser at http://127.0.0.1:8000/, and view your new users API. If you use the Login control in the top right corner youll also be able to add, create and delete users from the system. You can also interact with the API using command line tools such as curl. For example, to list the users endpoint: $ curl -H Accept: application/json; indent=4 -u admin:password http://127.0.0.1:8000/users/ [ { "url": "http://127.0.0.1:8000/users/1/", "username": "admin", "email": "admin@example.com", "is_staff": true, } ] Or to create a new user: $ curl -X POST -d username=new -d email=new@example.com -d is_staff=false -H Accept: application/json; indent=4 -u admin:password http://127.0.0.1:8000/users/ { "url": "http://127.0.0.1:8000/users/2/", "username": "new", "email": "new@example.com", "is_staff": false, } Documentation & Support Full documentation for the project is available at http://www.django-rest-framework.org. For questions and support, use the REST framework discussion group, or #restframework on freenode IRC. You may also want to follow the author on Twitter. Security If you believe youve found something in Django REST framework which has security implications, please do not raise the issue in a public forum. Send a description of the issue via email to rest-framework-security@googlegroups.com. The project maintainers will then work with you to resolve any issues where required, prior to any public disclosure.