Release notes Chiba 2
#####################

New features
============

* Windows support (Vista and upper).
* Better install wizard (UI, more tests, choose of languages)
* Advanced permissions for all natives applications.
* Comments application:

    * Administration interface
    * Emails are sent when new comments are posted, to post author and others commenters.

.. versionadded:: Chiba2.1

* Add media mass upload feature.

Developer
=========

Breaking changes
----------------

* :ref:`release/migrate_from_chiba.1_to_chiba.2/model_dataset`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/crud_success`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/attachment`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/comments`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/blognews`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/getUrlEnhanced`

Vendors update
--------------

* FuelPHP 1.6
* jQuery 1.9.1
* jQuery UI 1.10.3
* Wijmo 2013v1.4
* require.js 2.1.6

Improvements
------------

* **i18n**: :doc:`Default dictionary </app_create/translate>` ``app::default`` is used if no dictionary is set with ``Nos\I18n::current_dictionary()``.
* **DB**: Change interclassement on all columns containing a slug.
* **ORM**: Improvement of the model properties' cache mechanism, just one query of ``columns`` from DB by request.
* **ORM**: 4 new relation types, :ref:`twinnable_belongs_to <api:php/relations/twinnable_belongs_to>`, :ref:`twinnable_has_one <api:php/relations/twinnable_has_one>`, :ref:`twinnable_has_many <api:php/relations/twinnable_has_many>`, :ref:`twinnable_many_many <api:php/relations/twinnable_many_many>`.
* **ORM**: Model class, new ``addRelation()``, ``configModel()``, ``getApplication()`` methods.
* **Behaviour**: New :ref:`behaviour author <api:php/behaviours/author>`, used by Page, Media, Blog/News, Slideshow, Form.
* **Behaviour**: Refactoring ``behaviour`` implementation (:ref:`behaviours can intercept model events <api:php/behaviours/behaviour_event>`).
* **Behaviour Twinnable**: Models now can have :ref:`fields <api:php/behaviours/twinnable/configuration>`, :ref:`medias and WYSIWYGs <api:php/models/model/configuration>` common to all contexts.
* **Behaviour Twinnable**: new ``findMainOrContext()``, ``hasCommonFields()``, ``isCommonField()`` :ref:`methods <api:php/behaviours/twinnable/methods>`.
* **Behaviour URLEnhancer**: New :ref:`methods <api:php/behaviours/urlenhancer/methods>` ``deleteCacheEnhancer()`` and ``deleteCacheItem()``.
* **Behaviour URLEnhancer**: Delete front's cache of the item on deleting and updating.
* **Enhancer**: In the configuration popup, new ability to define a ``layout`` and ``fields`` :doc:`configuration </app_create/enhancer>` instead of a view, much like the CRUD.
* **Enhancer**: In :ref:`enhancer configuration <api:metadata/enhancers>`, new possible key ``valid_container``, which is callable. Can restrict the enhancer availability depending on container.
* **Enhancer**: The HTML output generated for the front-office is wrapped in a ``div`` with classes ``noviusos_enhancer`` and the enhancer name (``noviusos_blog``, ``noviusos_news``, ``noviusos_slideshow``, ``noviusos_form``)
* **Renderer**: New :ref:`datetime picker <api:php/renderers/datetime>` renderer to manage both date and time in the same input.
* **WYSIWYG**: :ref:`New WYSIWYG configuration mechanism <api:php/configuration/wysiwyg>`, with a ``wysiwygOptions`` event registrable by behaviour (and used by twinnable), and ``wysiwyg`` config sample file.
* **WYSIWYG**: In ``Nos::parse_wysiwyg()``, replacing anchors by ``URL#anchor`` only in front.
* **SEO**: :ref:`New friendly slug configuration mechanism <api:php/configuration/friendly_slug>`, with a ``friendlySlug`` event registrable by behaviour (and used by twinnable), and ``friendly_slug`` config sample file.
* **OsTabs**: :ref:`New reload method <api:javascript/$container/nosTabs>` in API.
* **OsTabs**: Change in tabs opening position. Tab added without index now is added at ``selected + 1``, excepted on the desktop, which always adds the new tab at the end.
* **Appdesk**: Two new keys, ``css`` and :ref:`notify <api:php/configuration/application/appdesk/notify>` in :ref:`appdesk configuration <api:php/configuration/application/appdesk>`.
* **Appdesk**: Ability to ignore a :ref:`cellFormatter <api:php/configuration/application/cellFormatters>` based on a column value.
* **Appdesk**: Now :ref:`custom cellFormatters <api:php/configuration/application/cellFormatters/custom>` are allowed in appdesks.
* **Grid**: New ``align`` key on :ref:`actions configuration <api:php/configuration/application/common/actions>`.
* **Grid**: New option for the :ref:`initial opening depth <api:php/configuration/application/appdesk/appdesk>` on tree grid.
* **UI**: Using ``.ui-priority-primary`` instead ``.primary`` on button and ``.title`` on textbox inputs.
* **UI**: Use browser native select, checkbox and radio, no more use of Wijmo widgets for those inputs.
* **Page**: Setting the home page is not allowed in multi-context view.
* **Page**: Deleting or unpublishing the home page is not allowed.
* **Page**: Increased title and url columns characters length.
* **Media**: New field ``filesize``. Display ``filesize`` and dimensions in appdesk preview and CRUD form.
* **Media**: Refactoring ``get_img_tag()`` and ``get_img_tag_resized()`` methods of :ref:`Model_Media <api:php/models/media/model_media/methods>`, uses ``HTML::img()`` for returning a tag with attributes.
* **Media**: You can now transform (crop, rotate, rounded, watermark, resize, shrink, grayscale, border) Media and Attachment images with :ref:`Toolkit_Image API <api:php/classes/toolkit_image>`.
* **Media**: New "Renew media's cache" action in Media appdesk toolbar, visible for expert users.
* **Media**: Increased title and url columns characters length.
* **Comments**: New API for use of ``noviusos_comments`` application.
* **Form**: New ``message`` view for the confirmation.
* **Blog/News**: :ref:`Thumbnail is now configurable (size & link) <api:applications/noviusos_blognews>`.
* **Misc**: New events :ref:`404.mediaFound <api:php/events/404.mediaFound>`, :ref:`404.attachmentFound <api:php/events/404.attachmentFound>`, :ref:`admin.loginFail <api:php/events/admin.loginFail>` and :ref:`nos.deprecated <api:php/events/nos.deprecated>`.
* **Misc**: All URLs are now urlencoded when use in a href or in a redirection.
* **Misc**: New ``temp`` directory in :file:`local/data`, assign to :ref:`novius-os.temp_dir <api:php/configuration/software>` config key by default.
* **Front**: ``is_preview`` is true only when you are logged in.

.. versionadded:: Chiba 2.1

* **Media**: Bugfix, images transformed was only display for users connected to back-office. For others, they return a ``403``.
* **Media**: Bugfix on media permissions; when updating a user, his writing rights on medias were disabled.
* **CRUD**: The configuration of button ``save`` is no more required in CRUD fields settings.
* **ORM**: In Models, when use ``cache_model_properties``, new possibility to set a callback (``check_property_callback``, see :file:`local/config/config.php.sample`) to check if the property is a potential unknow column, and avoid a ``show field`` SQL request.
* **Renderer**: New class ``Nos\Renderer`` for factorizing code between all renderers.
* **Templates basic**: Refactoring for better factorization of code between top and left menu templates.
* **Slideshow**: Refactoring configuration and organization. Widgets for displaying slideshow in front are manage by a formats config for better extendable.
* **Blog/News and Comments**: Better clean-up of front-cache when a post or a comment is inserted, updated or deleted.

.. versionadded:: Chiba 2.2

* **Renderer**: The class Nos\Renderer_Date_Picker was factorized into Nos\Renderer_Datetime_Picker
* **Media**: Media and folders deletions are manage by models, not by CRUD controller
* **i18n**: In the i18n class, adding addPriorityDictionary and addPriorityMessages methods
* **Tasks**: FuelPHP tasks have been adapted to Novius OS. Tasks namespace now depends on application namespaces allowing two tasks with similar names in many applications.
             A related application, `novius_taskmanager <https://github.com/novius/novius_taskmanager>`__, has been implemented in order to allow tasks management and execution from an browser.
* **Form**: Improve layout of the answer email.

.. versionadded:: Chiba 2.3

* **PHP**: Version 5.5 officialy supported
* **Renderer**: new option ``null_allowed`` (default to ``false``) on ``Nos\Renderer_Datetime_Picker``
* **Misc**: Improve ``Toolkit_Image->sizes()``, ``Media`` image is not loaded in memory
* **WYSIWYG**: In popup image, new fields border, align, vspace and hspace to easily update style
* **CRUD**: The javascript for context common fields is improved. Now, unsupported inputs can implement their own blocking process
* **CRUD**: Blocking process for context common fields is improved. Now it work also on not input fields (ie: renderer builded on a ``<div>``)
* **CRUD**: Blocking process for context common fields supports virtual name renderer fields
* **Profiler**: Some items from config are not displayed for security issues
* **Profiler**: New methods ``markDeltaStart()`` and ``markDeltaStop()`` to study time durations
* **ORM**: New parameter ``through_where`` in ``many_many`` relation configuration
* **Form**: Adding a ``replyto`` field to sending emails if an email is present in the answer. Depends on the ``add_replyto_to_first_email`` config key of ``noviusos_form.config.php`` file (default ``true``)
* **Form**: Move submit email field on the top of the admin form
* **AppWizard**: Added check on ``local/applications`` folder permission

.. versionadded:: Chiba 2.3.1

* **UI**: When inserting during a pick process, picks automatically the new item (media, page)

.. versionadded:: Chiba 2.3.2

* **Security**: Fix XSS in profiler

Deprecated
----------

* :ref:`release/migrate_from_chiba.1_to_chiba.2/enhancer`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/media`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/media_folder`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/page_link`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/user_login`

.. versionadded:: Chiba 2.1

* :ref:`release/migrate_from_chiba.1_to_chiba.2/renderer_selector`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/renderer_media`
* :ref:`release/migrate_from_chiba.1_to_chiba.2/slideshow`
