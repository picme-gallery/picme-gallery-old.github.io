## Summary
Have you ever gone on a trip, or gone to a party with friends, but forgot to take photos or ask your friends to send you the photos? 
Or have you ever come
home from an event with mostly photos of your friends or acquaintances, but with only a few blurry, questionable selfies of yourself? Are you tired of taking great photos of others, but not having any of your own to show off? Well fear no more, PicMe is the app for you.

PicMe, is an app that allows users who are out at an event, or who are traveling together to get access to a secure, cloud-based photo gallery via a shared user key.

With PicMe in your pocket, you'll no longer have to beg your friends and family to share those photos with you, only to have
them send some mediocre ones where they look good, but you're blinking or looking slightly less than stellar.

PicMe's goal is to 
help family and friends seamlessly exchange photos they have of each other through a private-shared gallery that uploads seamlessly, once an event or trip is underway. Just join the event, set your phone to party mode (for seamless-uploading), and enjoy access to the party gallery for up to 3 days after the event. After that your photos are deleted from the online gallery, and you get to keep the ones you've downloaded.

No need to mess with iMessage, Messenger, WhatsApp, Facebook, or Google Photos. If you have access to the private key for the gallery, just sign in, select your photos, download, and be on your way.

## [Intended users](work/intendedUsers.md)


* ## **Device & External services**

    The client component will need access to:
    1. [Native Camera App](https://developer.android.com/training/camera/photobasics)
        > This service will be used by PicMe Gallery to allow our users to upload photos directly from within our app, without having to switch back to the native camera app.
        This service is for convenience. If the service is interrupted, then the users will still be able to upload a photo by taking a picture, and then uploading it from their gallery (i.e. Google Photos, etc.) to PicMe Gallery.
    2. [App Data and Files](https://developer.android.com/guide/topics/data)
        > This service will be used by our app to complete the file-sharing portion of PicMe Gallery's features. It will allow users to save files on their phone.
        Simultaneously, this service will also allow users to share files (photos) to the galleries (events) that are hosted on the server or Web.
        If access to App Data and Files, or more specifically, the shared-storage and file-sharing that is a part of App Data and Files is interrupted, it will effectively render our app useless.
    
    3. [Google OAuth2.0](https://developers.google.com/assistant/identity/google-sign-in-oauth)
        > This service will be used by our app to keep track of our user-base. Furthermore, it will allow us to outsource some of the management of user info to Google.
        Essentially, we will be relying on Google for storing data associated to our users. 
        Without sign-in and authentication through Google services the PicMe Gallery will not be functional. We want to maintain some level of security and credibility over our user-base, while letting Google do the heavy-lifting.


[//]: # (Geo-fencing seems pretty rad though!. Maybe we can eventually use it? https://developer.android.com/training/location/geofencing However, we don't want our app to be dependent on it.)


## [Entity Classes](https://github.com/picme-gallery/picme-gallery-service/tree/master/src/main/java/edu/cnm/deepdive/picmegallery/model/entity)
* User
> A user entity class that contains information regarding when a user account was created, the user id key,
>and Google Oauth login credentials, amongst other things.
  
* Photo
> A photo entity class that contains the location and time-taken photo metadata, as well as, time when a photo is uploaded to the PicMe Gallery service.
>Additionally, it holds the information regarding which users uploaded which photo, as well as, the info on what event each photo is associated with.

* Event
> An event entity that acts as a _gallery_. It holds the event name, time, location, and password credentials required for
>access to upload photos to a PicMe Event. 

## [Entity-Relationship Diagram](work/entityRelationshipDiagram.md)
    
## [Team Ground Rules](ground-rules.md)