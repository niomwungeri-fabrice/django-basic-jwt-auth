=====
Accounts
=====

Accounts is a Django app to authenticate user using JWT Toke on custom users. 

Quick start
-----------
1. Add "accounts" to your INSTALLED_APPS setting like this::

    INSTALLED_APPS = [
        ...
        'accounts',
    ]
2. Include the polls URLconf in your project urls.py like this::

app_name = 'accounts'

urlpatterns = [
    path('register/', views.CreateAccountView.as_view(),
         name='user-register'),
    path('token/', jwt_views.TokenObtainPairView.as_view(),
         name='token_obtain_pair'),
    path('token/refresh/', jwt_views.TokenRefreshView.as_view(),
         name='token_refresh'),
    path('users/', views.UserListView.as_view(),
         name='user-list'),
    path('users/<uuid:id>/', views.UserDetailView.as_view(),
         name='user-detail'),
    path('me/', views.CurrentUserView.as_view(),
         name='me'),
]

3. Run `python manage.py migrate` to create the accounts models.

4. Start the development server

