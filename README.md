> **NOTE: This repository is no longer maintained since there is a better approach on how to achieve the same without even touching nginx'es codebase, see [nginx + a backend with a dynamic IP](http://dmitry.khlebnikov.net/2017/01/nginx-backend-with-dynamic-ip-eg-aws-elb.html)**
***

nginx-upstream-resolve
======================

A patch to the http nginx upstream module to allow the dynamic resolution
of the upstream servers.

One of the missing features that is available via the commercial
subscription of nginx is the ability to dynamically resolve the
upstream domain name.  This patch introduces this functionality
in the upstream compatible way, i.e. we are reusing the same
keyword to enable the dynamic resolution as the official
documentation uses.  This ensures that if time comes to use the
commercial subscription no configuration changes will be required.

This work was sponsored by [Openwall Pty Ltd](http://openwall.com.au)
and [Data Solutions Group Pty Ltd](http://www.data-solutions.com.au).

Repository structure
--------------------

The master branch points to the production ready patch for the latest
available version of the patch.  However, each time a patch is
regenerated for the new version of nginx the corresponding commit is
tagged with the nginx version the patch was generated for.  Therefore,
if you are building a package and are including this patch as the
part of your build you may want to refer to a particular versions of
the patch.

For example, if you are building nginx 1.10.1 then the URL to retrieve
the corresponding patch would be https://raw.githubusercontent.com/galaxy4public/nginx-upstream-resolve/1.10.1/nginx-upstream-resolve.diff
