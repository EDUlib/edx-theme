edx-theme
=========
Thème utilisé pour edX - EDUlib


sudo -H -u edxapp bash
cd /edx/app/edxapp
git clone https://github.com/EDUlib/edx-theme
mv themes themes.old
mv edx-theme themes
cd themes
mv themes default

placer la section suivante dans /edx/app/edxapp/lms.env.json
    "MKTG_URL_LINK_MAP": {
        "ABOUT" : "about",
        "FAQ" : "faq",
        "HONOR" : "honor",
        "TOS" : "tos",
        "COURSES" : "courses",
        "SCHOOLS" : « schools"
    },


cd /edx/app/edxapp/themes/edx-platform/lms/static/fonts/OpenSans
cp * /edx/app/edxapp/edx-platform/lms/static/fonts/OpenSans/

cd /edx/app/edxapp/themes/edx-platform/lms/static/images
cp * /edx/app/edxapp/edx-platform/lms/static/images/

cd /edx/app/edxapp/themes/edx-platform/lms/templates
cp index.html /edx/app/edxapp/edx-platform/lms/templates/

cd /edx/app/edxapp/themes/edx-platform/lms/templates/static_templates
cp * /edx/app/edxapp/edx-platform/lms/templates/static_templates/

cd /edx/app/edxapp/themes/edx-platform/cms/static/fonts/OpenSans
cp * /edx/app/edxapp/edx-platform/cms/static/fonts/OpenSans/

cd /edx/app/edxapp/themes/edx-platform/cms/static/img
cp * /edx/app/edxapp/edx-platform/cms/static/img

cd /edx/app/edxapp/themes/edx-platform/cms/static/sass
cp * /edx/app/edxapp/edx-platform/cms/static/sass


source /edx/app/edxapp/edxapp_env
cd /edx/app/edxapp/edx-platform
paver update_assets cms --settings=aws
paver update_assets lms --settings=aws
exit


sudo /edx/bin/supervisorctl -c /edx/etc/supervisord.conf restart edxapp:
sudo /edx/bin/supervisorctl -c /edx/etc/supervisord.conf restart edxapp_worker:


