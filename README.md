from django.urls import path, include
from rest_framework import routers

from . import api
from . import views

router = routers.DefaultRouter()
router.register(r'model11', api.Model11ViewSet)


urlpatterns = (
    # urls for Django Rest Framework API
    path('api/v1/', include(router.urls)),
)

urlpatterns += (
    # urls for Model11
    path('Model/model11/', views.Model11ListView.as_view(), name='Model_model11_list'),
    path('Model/model11/create/', views.Model11CreateView.as_view(), name='Model_model11_create'),
    path('Model/model11/detail/<slug:slug>/', views.Model11DetailView.as_view(), name='Model_model11_detail'),
    path('Model/model11/update/<slug:slug>/', views.Model11UpdateView.as_view(), name='Model_model11_update'),
)
