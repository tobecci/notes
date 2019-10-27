# Django notes

## creating views
```py
from django.views.generic import TemplateView

class HomePageView(TemplateView):
    template_name = 'home.html'

class AboutPageView(TemplateView):
    template_name = 'about.html'
```

## passing data 

```py
from django.views.generic import TemplateView, ListView
class IndexView(ListView):
    model = User
    template_name = 'users/index.html'
    context_object_name = 'user_list'
    # we access the object in the view as user_list 
```