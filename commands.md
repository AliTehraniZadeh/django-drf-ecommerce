<!-- برای ساختن تنظیمات مختلف برای حالت اجرا و لوکال
ابتدا فولدر setting می سازیم
base.py, local.py, production.py می سازیم
بالای همه می نویسیم from .base import * -->

<!-- این متن داخل manage.py -->
from drfecommerce.settings import base 

def main():

    if base.DEBUG:
        os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'drfecommerce.settings.local')
    else:
        os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'drfecommerce.settings.production')


<!-- in python shell -->
from django.core.management.utils import get_random_secret_key
print(get_random_secret_key())

pip install -r requirements.txt

pip install python-dotenv