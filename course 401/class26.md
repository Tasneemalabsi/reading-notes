# Permissions & Postgresql

In DRF, permissions, along with authentication and throttling, are used to grant or deny access for different classes of users to different parts of an API.

Authentication and authorization work hand in hand. Authentication is always executed before authorization.

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.

## How permissions are determined

*When the permissions checks fail either a "403 Forbidden" or a "401 Unauthorized" response will be returned, according to the following rules:*
- The request was successfully authenticated, but permission was denied. — An HTTP 403 Forbidden response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers. — An HTTP 403 Forbidden response will be returned.
- The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. — An HTTP 401 Unauthorized response, with an appropriate WWW-Authenticate header will be returned.

## Object level permissions

*Object level permissions are run by REST framework's generic views when .get_object() is called. As with view level permissions, an exceptions.PermissionDenied exception will be raised if the user is not allowed to act on the given object.*

*This will either raise a PermissionDenied or NotAuthenticated exception, or simply return if the view has the appropriate permissions.*

```
def get_object(self):
    obj = get_object_or_404(self.get_queryset(), pk=self.kwargs["pk"])
    self.check_object_permissions(self.request, obj)
    return obj
```

## Setting the permission policy

```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

*You can also set the authentication policy on a per-view, or per-viewset basis, using the APIView class-based views.*

```
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)
```

## API Reference

### AllowAny

The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

### IsAuthenticated

The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.

### IsAdminUser

The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

### IsAuthenticatedOrReadOnly

The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.

## DjangoModelPermissions

Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.

- POST requests require the user to have the add permission on the model.
- PUT and PATCH requests require the user to have the change permission on the model.
- DELETE requests require the user to have the delete permission on the model.

## DjangoObjectPermissions

 Authorization will only be granted if the user is authenticated and has the relevant per-object permissions and relevant model permissions assigned.

- POST requests require the user to have the add permission on the model instance.
- PUT and PATCH requests require the user to have the change permission on the model instance.
- DELETE requests require the user to have the delete permission on the model instance.

Note that DjangoObjectPermissions does not require the django-guardian package, and should support other object-level backends equally well.

## Custom permissions

*To implement a custom permission, override BasePermission and implement either, or both, of the following methods:*

- .has_permission(self, request, view)
- .has_object_permission(self, request, view, obj)

Custom permissions will raise a PermissionDenied exception if the test fails. To change the error message associated with the exception, implement a message attribute directly on your custom permission.

```
from rest_framework import permissions

class CustomerAccessPermission(permissions.BasePermission):
    message = 'Adding customers not allowed.'

    def has_permission(self, request, view):
```

## Overview of access restriction methods

- `queryset/get_queryset()` : Limits the general visibility of existing objects from the database. The queryset limits which objects will be listed and which objects can be modified or deleted. The get_queryset() method can apply different querysets based on the current action.
- `permission_classes/get_permissions()` : General permission checks based on the current action, request and targeted object. Object level permissions can only be applied to retrieve, modify and deletion actions. Permission checks for list and create will be applied to the entire object type. (In case of list: subject to restrictions in the queryset.)
- `serializer_class/get_serializer()` : Instance level restrictions that apply to all objects on input and output. The serializer may have access to the request context. The get_serializer() method can apply different serializers based on the current action.

## Third party packages

- DRF - Access Policy
- REST Condition
- DRY Rest Permissions
- Django Rest Framework Roles
- Django REST Framework API Key
- Django Rest Framework Role Filters
- Django Rest Framework PSQ





