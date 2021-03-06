# Change Log

## [2.2.1] - 2018-10-06

    * Resolves deprecation warnings and adopt recommendations in unit tests.
    * Fixes demo sites so that they work with Django 1.11, Django 2.0 and
      Django 2.1.

## [2.2.0] - 2018-08-12

    * Adds support for Django 2.1.
    * Drops support for Django < 1.11 as it depends on django-contrib-comments
      which dropped support too.
    * Fixes issue 104 (on lack of Django 2.1 support).

## [2.1.0] - 2018-02-13

    * Fixes issues #76, #86 and #87.
    * Request user name and/or email address in case the user is logged
      in but the user's email attribute is empty and/or the user's
      get_full_name() method returns an empty string.

## [2.0.10] - 2018-01-19

	* Adds Django 2.0 compatibility.
	* Fixes issues #81 and #83.
	* Replaces the use of django.test.client by RequestFactory in unittests.

## [2.0.9] - 2017-11-09

	* Fix issue 77. Template filter xtd_comment_gravatar_url must not
	  hard-code http schema in URL (reported by @pamost).

## [2.0.8] - 2017-09-24

	* App translation to Finnish, thanks to Tero Tikkanen (@terotic).

## [2.0.7] - 2017-09-20

	* Adds missing migration for a field's label (issue 71).
	* Makes the form label for field 'name' translatable (issue 73).

## [2.0.6] - 2017-08-08

	* Code fixes to enable proper support for the Django Sites Framework.
	* Code fixes for the `comp` demo site.
	* Makes demo site dates in initial data files timezone aware.
	* Improves documentation on setting up demo sites.
	* Style changes in CSS wells.

## [2.0.5] - 2017-07-20

	* Surpass version number to fix problem with package upload in PyPI.
	* No changes applied to this version.

## [2.0.4] - 2017-07-19

	* Use `django.core.signing` with temporary comment passed in URL
	  redirection.
	* Fix mistakes in documentation.

## [2.0.3] - 2017-07-10

	* App translation to French thanks to Brice Gelineau.
	* Fixed MANIFEST.in file, so that files with translations are
	  distributed.

## [2.0.0] - 2017-06-04

	* Javascript plugin (based on ReactJS).
	* Web API to:
	  * Create a comment for a given content type and object ID.
	  * List comments for a given content type and object ID.
	  * Send feedback flags (like/dislike) on comments.
	  * Send report flag (removal suggestion) for a comment.
	  * Template filter `has_permission` applicable to a user object and
	    accepting a string specifying the `app_label.permission` being
	    checked. It returns `True` if the user has the given permission,
	    otherwise returns False.
	* Setting `COMMENTS_XTD_API_USER_REPR` defines a lambda function to
	  return the user string representation used by the web API in response
	  objects.
	* Setting `COMMENTS_XTD_APP_MODEL_PERMISSIONS` to explicitly define what
	  commenting features are enabled on per app.model basis.
	* Templates `comments/delete.html` and `comments/deleted.html` matching
	  django-comments-xtd default twitter-bootstrap styling.
	* Dependencies on Python packages: djangorestframework.
	* Supports i18n for English and Spanish.
	* All settings namespaced inside the COMMENTS_XTD setting.
	* Management command to migrate comments from django-contrib-comments to
	  django-comments-xtd.
	* Enable removal link in `django_comments_xtd/comment_tree.html` when the
	  user has the permission `django_comments.can_moderate`.
	* Changed, when the user logged has `django_comments.can_moderate` permission,
	  template `django_comments_xtd/comment_tree.html` will show the number of
	  removal suggestions a comment has received.
	* Changed, when a comment is marked as removed by a moderator
	  (using django-comments' `comments-delete` url) every nested comment below
	  the one removed is unpublished (`is_public` attribute is turned to
	  `False`).
	* Changed view helper functions, `perform_like` and `perform_dislike` now
	  returns a boolean indicating whether a flag was created. If `True` the flag
	  has been created. If `False` the flag has been deleted. These two functions
	  behave as toggle functions.
	* Changed templates `comments/preview.html`, `comments/flag.html` and
	  `comments/flagged.hml`.
	* Removed dependency on django-markup.
	* Removed template filter `render_markup_comment`.
	* Removed setting `MARKUP_FALLBACK_FILTER`.
