# Calling Django Components from a Pure Python Script

In many cases, it's handy to be able to access the Django ORM from a pure python script. Sometimes I'm writing a one-off database script that I don't need to refer back to. Other times I'm doing something that would be a scratch paper implementation that I'll never use again. For something reusable that would useful to run on the server periodically it's often better to use a Django management command. But if it's really one-off, here's how to call django components from a pure Python script.

The two steps are configuring settings and calling setup. To configure settings, either set the `DJANGO_SETTINGS_MODULE` environment variable or call `settings.configure()`. Then call `django.setup()`. So to access django componenets through a project called `my_project`:

```python
os.environ['DJANGO_SETTINGS_MODULE'] = 'my_project.settings'
django.setup()
```

or to start with django's default settings and change what you like, use:

```python
settings.configure()
django.setup()
```

You can pass specific values to `configure`, for instance

```python
settings.configure(DEBUG=True)

```

Don't import the django models or whatever you're trying to access until after calling `setup`.


Links:

- [Django Setting Module or Configure](https://docs.djangoproject.com/en/5.0/topics/settings/#either-configure-or-django-settings-module-is-required)
- [Django Setup](https://docs.djangoproject.com/en/5.0/topics/settings/#calling-django-setup-is-required-for-standalone-django-usage)
