# Calling Django Components from a Pure Python Script

In many cases, it's handy to be able to access the ORM from a pure python script. For instance, if you're writing a one-off database script, or if doing something that would be a scratch paper implementation that you'll never use again. Of course, if you think it would useful to run on the server periodically you would do better to use a Django management command. But if it's really one-off, you might prefer a pure Python script.

The two steps are to configure settings and call `django.setup()`. To configure settings, either set the `DJANGO_SETTINGS_MODULE` environment variable or call `settings.configure()`. Then call `django.setup()`. So for a django project called `my_project`:

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


Links:

[Django Setting Module or Configure](https://docs.djangoproject.com/en/5.0/topics/settings/#either-configure-or-django-settings-module-is-required)
[Django Setup](https://docs.djangoproject.com/en/5.0/topics/settings/#calling-django-setup-is-required-for-standalone-django-usage)
