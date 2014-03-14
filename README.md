Drupal module to force logged-in users to access all pages over https.

Once a user authenticates, no matter their role, they will always be redirected to the https version of any page they try to access.

Obviously you need to make sure SSL is enabled for your site.

To install, just upload to your sites/*/modules folder and enable. Once enabled, log out, then log in again. That's all, it should work.

There are no configuration options.

URL fragments are not preserved across redirects, so that if a user accesses http://example.com/foo/bar#fragment they will be redirected to https://example.com/foo/bar (i.e. without the #fragment).

To disable on local/dev instances, either disable the module (obviously), or define the following PHP constant somewhere prior to module load:

```php
define('__ENV__', 'local');
```