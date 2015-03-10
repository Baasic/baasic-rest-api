
### Key Value

* **key-values**
  * [DELETE] (keyvalue-delete)
  * [GET (By Search Criteria)] (keyvalue-get-by-search-criteria)
  * [GET] (keyvalue-get)
  * [POST] (keyvalue-post)
  * [PUT] (keyvalue-put)



### Value Set

* **value-sets**
  * [DELETE] (valueset-delete)
  * [GET (By Search Criteria)] (valueset-get-by-search-criteria)
  * [GET] (valueset-get)
  * [POST] (valueset-post)
  * [PUT] (valueset-put)
  * **items**
    * [DELETE] (valueset-items-delete)
    * [GET (By Search Criteria)] (valueset-items-get-by-search-criteria)
    * [GET] (valueset-items-get)
    * [POST] (valueset-items-post)
    * [PUT] (valueset-items-put)



### Article

* **article**
  * **settings**
    * [GET] (article-settings-get)
    * [PUT] (article-settings-put)
  * **ratings**
    * [DELETE] (article-rating-delete)
    * [GET (By Search Criteria)] (article-rating-get-by-search-criteria)
    * [GET] (article-rating-get)
    * [GET (By User)] (article-rating-get-by-user)
  * **tags**
    * [DELETE] (article-tag-delete)
    * [GET] (article-tag-get)
    * [GET (By Search Criteria)] (article-tag-get-by-search-criteria)
    * [POST] (article-tag-post)
    * [PUT] (article-tag-put)

* **articles**
  * [DELETE] (article-delete)
  * [GET (By Search Criteria)] (article-get-by-search-criteria)
  * [GET] (article-get)
  * [POST] (article-post)
  * [PUT] (article-put)
  * **tags**
    * [DELETE (All)] (article-tag-delete-by-article-all)
    * [DELETE] (article-tag-delete-by-article)
    * [GET] (article-tag-get-by-article)
    * [GET (By Search Criteria)] (article-tag-get-by-article-search-criteria)
    * [POST (Tag)] (article-tag-post-by-article-tag)
    * [POST] (article-tag-post-by-article-entry)
  * **ratings**
    * [DELETE] (article-rating-delete-by-article)
    * [GET] (article-rating-get-by-article)
    * [POST] (article-rating-post)
    * [PUT] (article-rating-put)
  * **users-ratings**
    * [GET] (article-rating-get-by-article-search-criteria)
  * **archive**
    * [PUT] (article-put-archive)
  * **publish**
    * [PUT] (article-put-publish)
  * **purge**
    * [DELETE] (article-delete-all)
  * **restore**
    * [PUT] (article-put-restore)
  * **unpublish**
    * [PUT] (article-put-unpublish)
  * **permissions**
    * [GET] (article-acl-get)
    * [PUT] (article-acl-put)
    * **actions**
      * **roles**
	    * [DELETE] (article-acl-delete-by-role)
      * **users**
	    * [DELETE] (article-acl-delete-by-user)



### Dynamic Type

* **resources**
  * [DELETE] (resource-delete)
  * [GET (By Search Criteria)] (resource-get-by-search-criteria)
  * [GET] (resource-get)
  * [PATCH] (resource-patch)
  * [POST] (resource-post)
  * [PUT] (resource-put)
  * **permissions**
    * [GET] (resource-acl-get)
    * [PUT] (resource-acl-put)
    * **actions**
      * **roles**
	    * [DELETE] (resource-acl-delete-by-role)
      * **users**
	    * [DELETE] (resource-acl-delete-by-user)

* **schemas**
  * [DELETE] (schema-delete)
  * [GET] (schema-get)
  * [GET (By Search Criteria)] (schema-get-by-search-criteria)
  * [POST] (schema-post-insert)
  * [PUT] (schema-put)
  * **generate**
    * [POST] (schema-post-generate)



### Membership

* **login**
  * [DELETE] (login-delete)
  * [GET] (login-get)
  * [POST] (login-post)
  * [PUT] (login-put)

* **permissions**
  * [POST] (permissions-post)
  * **sections**
    * [GET] (permissions-get-by-search-criteria)
    * **actions**
      * **roles**
	    * [DELETE] (permissions-delete-by-role)
      * **users**
	    * [DELETE] (permissions-delete-by-username)
  * **actions**
    * [GET] (permissions-get)
    * [GET (By Search String)] (permissions-get-by-search-string)

* **roles**
  * [DELETE] (role-delete)
  * [GET (By Search Criteria)] (role-get-by-search-criteria)
  * [GET] (role-get)
  * [POST] (role-post)
  * [PUT] (role-put)

* **recover-password**
  * [POST] (recover-password-post)
  * [PUT] (recover-password-put)

* **users**
  * [DELETE] (user-delete)
  * [GET] (user-get)
  * [GET (By Search Criteria)] (user-get-by-search-criteria)
  * [POST] (user-post)
  * [PUT] (user-put-update)
  * **approve**
    * [PUT] (user-put-approve)
  * **disapprove**
    * [PUT] (user-put-disapprove)
  * **lock**
    * [PUT] (user-put-lock)
  * **unlock**
    * [PUT] (user-put-unlock)
  * **change-password**
    * [PUT] (user-put-update-password)
  * **exists**
    * [GET] (user-get-checkusername)

* **register**
  * [POST] (register-post)
  * **activate**
    * [PUT] (register-put)



### Application

* **applications**
  * [DELETE] (applications-delete)
  * [GET] (applications-get)
  * [PUT] (applications-put)
  * **activate**
    * [PUT] (applications-put-activate)
  * **deactivate**
    * [PUT] (applications-put-deactivate)



### Subscription System

* **subscriptions**
  * [GET] (subscription-get-whole-segment)
  * [GET (Part)] (subscription-get-segment-part)
  * [POST] (subscription-post-whole-segment)
  * [POST (Part)] (subscription-post-segment-part)
  * [DELETE] (subscription-delete-whole-segment)
  * [DELETE (Part)] (subscription-delete-segment-part)
  * **users**
    * [GET] (subscription-get-whole-segment-user)
    * [GET (Part)] (subscription-get-segment-part-user)
    * [POST] (subscription-post-whole-segment-user)
    * [POST (Part)] (subscription-post-segment-part-user)
    * [DELETE] (subscription-delete-whole-segment-user)
    * [DELETE (Part)] (subscription-delete-segment-part-user)



### Core

* **lookups**
  * [GET] (lookup-get)



### Version

* **versions**
  * [GET] (version-get-applications)


