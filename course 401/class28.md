# API Deployment

## Managing Django Settings: Issues

- Different environments. Usually, you have several environments: local, dev, ci, qa, staging, production, etc. 
- Sensitive data. You have SECRET_KEY in each Django project. On top of this there can be DB passwords and tokens for third-party APIs like Amazon or Twitter. This data cannot be stored in VCS.
- Sharing settings between team members. You need a general approach to eliminate human error when working with the settings. 
- Django settings are a Python code. This is a curse and a blessing at the same time.

## Setting Configuration

The basic idea of this method is to extend all environment-specific settings in the settings_local.py file, which is ignored by VCS.

**Example:**

```
ALLOWED_HOSTS = ['example.com']
DEBUG = False
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'production_db',
        'USER': 'user',
        'PASSWORD': 'password',
        'HOST': 'db.example.com',
        'PORT': '5432',
        'OPTIONS': {
            'sslmode': 'require'
        }
    }
}
```

### Separate settings file for each environment

*In this case, you make a settings package with the following file structure:*

```
settings/
   ├── __init__.py
   ├── base.py
   ├── ci.py
   ├── local.py
   ├── staging.py
   ├── production.py
   └── qa.py
```

- You need to find a way to handle secret passwords and tokens.
- “Inheritance” of settings can be hard to trace and maintain.


**Environment variables**

import os

```
SECRET_KEY = os.environ['SECRET_KEY']
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ['DATABASE_NAME'],
        'HOST': os.environ['DATABASE_HOST'],
        'PORT': int(os.environ['DATABASE_PORT']),
    }
}
```

*To fix KeyError, you can write your own custom wrapper. For example:*

```
import os

from django.core.exceptions import ImproperlyConfigured


def get_env_value(env_variable):
    try:
      	return os.environ[env_variable]
    except KeyError:
        error_msg = 'Set the {} environment variable'.format(var_name)
        raise ImproperlyConfigured(error_msg)


SECRET_KEY = get_env_value('SECRET_KEY')
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': get_env_value('DATABASE_NAME'),
        'HOST': get_env_value('DATABASE_HOST'),
        'PORT': int(get_env_value('DATABASE_PORT')),
    }
}
```

## 12 Factors

*12 Factors is a collection of recommendations on how to build distributed web-apps that will be easy to deploy and scale in the Cloud.*

**As the name suggests, the collection consists of twelve parts:**

- Codebase
- Dependencies
- Config
- Backing services
- Build, release, run
- Processes
- Port binding
- Concurrency
- Disposability
- Dev/prod parity
- Logs
- Admin processes

### django-environ

Writing code using os.environ could be tricky sometimes and require additional effort to handle errors. It’s better to use django-environ instead.


**Technically it’s a merge of:**

- envparse
- honcho
- dj-database-url
- dj-search-url
- dj-config-url
- django-cache-url

## Django Settings: Best practices
- Keep settings in environment variables.
- Write default values for production configuration.
- Don’t hardcode sensitive settings, and don’t put them in VCS.
- Split settings into groups: Django, third-party, project.
- Follow naming conventions for custom settings.

## How Does SSH Work

*SSH, or Secure Shell, is a remote administration protocol that allows users to control and modify their remote servers over the Internet.*

**The Figure Below shows a typical SSH Window. Any Linux or macOS user can SSH into their remote server directly from the terminal window.**

![ssh](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/shell-snapshot.jpg)

### SSH works by:

For Mac and Linux users, head over to your terminal program and then follow the procedure below:

**The SSH command consists of 3 distinct parts:**

`ssh {user}@{host}`

- The SSH key command instructs your system that you want to open an encrypted Secure Shell Connection. 
- {user} represents the account you want to access. For example, you may want to access the root user, which is basically synonymous for system administrator with complete rights to modify anything on the system. 
- {host} refers to the computer you want to access. 

### Understanding Different Encryption Techniques

*There are three different encryption technologies used by SSH:*

1. Symmetrical encryption
2. Asymmetrical encryption
3. Hashing.

### Symmetric Encryption


![encryption](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.jpg)


Symmetrical encryption is often called shared key or shared secret encryption. 

Symmetric keys are used to encrypt the entire communication during a SSH Session. Both the client and the server derive the secret key using an agreed method, and the resultant key is never disclosed to any third party. 

### Asymmetric Encryption

![asymmetric](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/asymmetric-encryption.jpg)


The public key, as the name suggest is openly distributed and shared with all parties. While it is closely linked with the private key in terms of functionality, the private key cannot be mathematically computed from the public key.

### Hashing

![hash](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-tutorial-hash.jpg)

SSH uses hashes to verify the authenticity of messages. This is done using HMACs, or Hash-based Message Authentication Codes. 

### How Does SSH Work with These Encryption Techniques

The way SSH works is by making use of a client-server model to allow for authentication of two remote systems and encryption of the data that passes between them.

![ssh-works](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-client-and-server.jpg)

### Session Encryption Negotiation

When a client tries to connect to the server via TCP, the server presents the encryption protocols and respective versions that it supports.


