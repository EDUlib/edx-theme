edx-theme
=========
Thème utilisé pour edX - EDUlib


* sudo -H -u edxapp bash
* cd /edx/app/edxapp
* git clone https://github.com/EDUlib/edx-theme
* mv themes themes.old
* mv edx-theme themes
* cd themes
* mv themes default

placer la section suivante dans /edx/app/edxapp/lms.env.json
    "MKTG_URL_LINK_MAP": {
        "ABOUT" : "about",
        "FAQ" : "faq",
        "HONOR" : "honor",
        "TOS" : "tos",
        "COURSES" : "courses",
        "SCHOOLS" : « schools"
    },


cd /edx/app/edxapp/themes/edx-platform/lms/static/images
cp * /edx/app/edxapp/edx-platform/lms/static/images/

mv /edx/app/edxapp/edx-platform/lms/static/images/bulk_email /edx/app/edxapp/edx-platform/lms/static/images/bulk_email.1
mv /edx/app/edxapp/edx-platform/lms/static/images/default-theme /edx/app/edxapp/edx-platform/lms/static/images/default-theme.1
mv /edx/app/edxapp/edx-platform/lms/static/images/edx-theme /edx/app/edxapp/edx-platform/lms/static/images/edx-theme.1
mv /edx/app/edxapp/edx-platform/lms/static/images/social /edx/app/edxapp/edx-platform/lms/static/images/social.1

mv bulk_email default-theme edx-theme social /edx/app/edxapp/edx-platform/lms/static/images/


cd /edx/app/edxapp/themes/edx-platform/lms/templates
cp index.html /edx/app/edxapp/edx-platform/lms/templates/
cp course.html /edx/app/edxapp/edx-platform/lms/templates/
cp footer.html /edx/app/edxapp/edx-platform/lms/templates/
cp navigation.html /edx/app/edxapp/edx-platform/lms/templates/
cp courseware/courses.html /edx/app/edxapp/edx-platform/lms/templates/courseware

cd /edx/app/edxapp/themes/edx-platform/lms/templates/static_templates
cp * /edx/app/edxapp/edx-platform/lms/templates/static_templates/

cd /edx/app/edxapp/themes/edx-platform/lms/templates/wiki
cp * /edx/app/edxapp/edx-platform/lms/templates/wiki
cd /edx/app/edxapp/themes/edx-platform/lms/templates/wiki/includes
cp * /edx/app/edxapp/edx-platform/lms/templates/wiki/includes
cd /edx/app/edxapp/themes/edx-platform/lms/templates/wiki/includes/_notes
cp * /edx/app/edxapp/edx-platform/lms/templates/wiki/includes/_notes

cd /edx/app/edxapp/themes/edx-platform/cms/static/sass
cp * /edx/app/edxapp/edx-platform/cms/static/sass

cd /edx/app/edxapp/themes/edx-platform/cms/templates
cp *.html /edx/app/edxapp/edx-platform/cms/templates
cd /edx/app/edxapp/themes/edx-platform/cms/templates/widgets
cp *.html /edx/app/edxapp/edx-platform/cms/templates/widgets

cd /edx/app/edxapp/themes/
cp server-error.html /edx/app/edxapp/edx-platform/lms/templates/static_templates/server-error.html







source /edx/app/edxapp/edxapp_env
cd /edx/app/edxapp/edx-platform
paver update_assets cms --settings=aws
paver update_assets lms --settings=aws
exit


sudo /edx/bin/supervisorctl restart edxapp:
sudo /edx/bin/supervisorctl restart edxapp_worker:


