#### [Entity Classes](https://github.com/picme-gallery/picme-gallery-service/tree/database/src/main/java/edu/cnm/deepdive/picmegallery/model/entity)
* User
> A user entity class that contains information regarding when a user account was created, the user id key,
>and Google Oauth login credentials, amongst other things.
  
* Photo
> A photo entity class that contains the location and time-taken photo metadata, as well as, time when a photo is uploaded to the PicMe Gallery service.
>Additionally, it holds the information regarding which users uploaded which photo, as well as, the info on what event each photo is associated with.

* Event
> An event entity that acts as a _gallery_. It holds the event name, time, location, and password credentials required for
>access to upload photos to a PicMe Gallery event. 

