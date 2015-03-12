edx-theme
=========
Thème utilisé pour edX - EDUlib


* sudo -H -u edxapp bash
* cd /edx/app/edxapp
* git clone https://github.com/EDUlib/edx-theme
* mv themes themes.old
* mv edx-theme themes
* cd themes
* mv themes/default default 

placer la section suivante dans /edx/app/edxapp/lms.env.json
    "MKTG_URL_LINK_MAP": {
        "ABOUT" : "about",
        "FAQ" : "faq",
        "HONOR" : "honor",
        "TOS" : "tos",
        "COURSES" : "courses",
        "SCHOOLS" : « schools"
    },

* cd /edx/app/edxapp/themes
* cp server-error.html /edx/app/edxapp/edx-platform/lms/templates/static_templates/server-error.html

* cd /edx/app/edxapp/themes/cms/static/images/edx-theme
* cp * /edx/app/edxapp/edx-platform/cms/static/images/

* cd /edx/app/edxapp/themes/cms/static/sass
* cp _base.scss /edx/app/edxapp/edx-platform/cms/static/sass
* cp  _variables.scss /edx/app/edxapp/edx-platform/cms/static/sass
* cp elements/_header.scss /edx/app/edxapp/edx-platform/cms/static/sass/elements/

* cd /edx/app/edxapp/themes/cms/templates
* cp 404.html  500.html  error.html /edx/app/edxapp/edx-platform/cms/templates/
* cp widgets/* /edx/app/edxapp/edx-platform/cms/templates/widgets/

* cd /edx/app/edxapp/themes/lms/static/images
* cp bulk_email/* /edx/app/edxapp/edx-platform/lms/static/images/bulk_email
* cp default-theme/* /edx/app/edxapp/edx-platform/lms/static/images/default-theme
* mv default-theme/institutions /edx/app/edxapp/edx-platform/lms/static/images/default-theme
* cp edx.png /edx/app/edxapp/edx-platform/lms/static/images/
* cp edx-theme/* /edx/app/edxapp/edx-platform/lms/static/images/edx-theme
* cp edx-theme/_notes/* /edx/app/edxapp/edx-platform/lms/static/images/edx-theme/_notes/
* cp favicon_edx.ico favicon.ico linkedin_add_to_profile.png logo_bw.png logo.png openedx-logo-tag-dark.png openedx-logo-tag_en.png openedx-logo-tag-light.png openedx-logo-tag.png /edx/app/edxapp/edx-platform/lms/static/images
* cp social/* /edx/app/edxapp/edx-platform/lms/static/images/social
* cp social/_notes/* /edx/app/edxapp/edx-platform/lms/static/images/social/_notes/

* cd /edx/app/edxapp/themes/lms/templates
* cp course.html footer.html index.html main.html navigation.html /edx/app/edxapp/edx-platform/lms/templates/
* cp courseware/* /edx/app/edxapp/edx-platform/lms/templates/courseware/
* cp static_templates/* /edx/app/edxapp/edx-platform/lms/templates/static_templates/
* cp wiki/includes/_notes/* /edx/app/edxapp/edx-platform/lms/templates/wiki/includes/_notes 


* source /edx/app/edxapp/edxapp_env
* cd /edx/app/edxapp/edx-platform
* paver update_assets cms --settings=aws
* paver update_assets lms --settings=aws
* exit


* sudo /edx/bin/supervisorctl restart edxapp:
* sudo /edx/bin/supervisorctl restart edxapp_worker:


