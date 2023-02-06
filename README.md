# Scoped Storage
 ### Intro ###
The goal of scoped storage is to protect the privacy of app and user data. This includes protecting user information (such as photo metadata), preventing apps from modifying or deleting user files without explicit permission, and protecting sensitive user documents downloaded to Download or other folders.
 
 ## Internal Storage
- Every app has its own private directory in internal storage and this directory is not visible to any other app except if your phone is rooted.
- Everything else is considered shared or external storage

## External Storage
- On one hand a lot of apps need the `READ_EXTERNAL_STORAGE` permission but most of them only just do simple things with it. They don’t need to access the whole storage but they could.
- On other hand apps often leave files somewhere in external storage and when they are uninstalled they still take up space.
- Sol: **Scoped Storage** solved this.

## Scoped Storage
- It was introduced in android 10 (API 29 - Q) but only mandatory from android 11 (API 30 - R) onwards.
- Now the system knows which app created which files so these files can be removed once an app is uninstalled.
- Also, every app can fully access their own directories in shared storage and every app can save media files in collections without permission. But if we want to change files that we don’t own that we didn’t create with our app, then we can do that with the functions `createWriteRequest` or `createDeleteRequest` but this will need user’s approval now.
- We can also put files in trash instead of deleting them. These items in trash can will be deleted after 30 days but can be recovered until then.
- But some apps need write access to the whole storage like file managers. For that there was new permission `MANAGE_EXTERNAL_STORAGE` . But this permission needs manual review on google play submission so they will check if your app really needs that permission.
- Scoped storage improved the user’s privacy while limiting the freedom developers have.

