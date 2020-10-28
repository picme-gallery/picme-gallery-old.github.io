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

## Intended users

* People who go to lots of events like concerts, music festivals, state fairs, graduations, weddings, baby-showers, and birthday parties, etc.

    > As a party-goer, I want to have an app that easily allows me to get access to the photos taken of me at a party, so that I can later upload them to social media and share them with my friends.

* People who travel frequently to new destinations, both nationally and internationally.

    > As someone who travels often internationally and makes new friends with strangers during my travels, I want an app that seamlessly allows me to share the great photos I take of my new friends with them even if I forget to get their social media info or if we don't speak the same language, so that I
share those photos with them, have a memento, and foster a deeper connection.

* People who are working on raising awareness around a cause or issue important to them and their local community.

    > As someone who is involved in local politics, I want an app that allows me to get access to the photos from all the people's camera rolls who attend local rallies and
protests such as those from the Black Lives Matter movement, so that I can share and show photos that prove our cause to the media and journalists, whatever our cause may be.

* People who use online dating apps

    > As someone who is new to online dating, I want an app to help me get access to some nice candid photos of myself that my friends have taken in the past , so that I can more easily get dates and find love and maybe a glimmer of hope during the pandemic.
    
* People who browse social media a lot, but don't post very often

    > As someone who browses social media often, but doesn't post much, I want an app that helps me get access to the photos my more social friends have taken of me during our adventures, so that I can have access to those good photos of myself and feel comfortable to post them. 




## Client component

* **Functionality**

    The UI of PicMe, will allow users to log in and authenticate using [Google OAuth2.0](https://developers.google.com/assistant/identity/google-sign-in-oauth), it will allow them to enter a key **(created and distributed by the moderator or party organizer)** to access recent **galleries (parties)** from the home page of the app, and once they're within the gallery users will be able to select photos to download from the shared, event gallery **(party)**.  It will be a clean, simple, & aesthetic app.
    
    Without sign-in and authentication through Google services the App will not be functional. We want to maintain some level of security and credibility over our user-base. 
    
* **Persistent data**

    The current plan is to avoid persistent data on the device, other than user credentials for authorized log-in using OAuth 2.0. Also, there will probably be a flag to check if the photos on the device have already been uploaded to the shared-cloud gallery, to avoid duplicates in the gallery.

* **Device/external services**

    The client component will need access to:
    1. [Native Camera App](https://developer.android.com/training/camera/photobasics)
        > This service will be used by PicMe Gallery to allow our user's to upload photos directly from within our app, without having to switch back to the native camera app.
        This service is for convenience. If the service is interrupted, then the users will still be able to upload a photo by taking a picture, and then uploading it to PicMe Gallery.
    2. [App Data and Files](https://developer.android.com/guide/topics/data)
        > This service will be used by our app to complete the file-sharing portion of PicMe Gallery's features. It will allow users to save files on their phone.
        Simultaneously, this service will also allow users to share files (photos) to the gallery (Events) that is hosted on the server or Web.
        If access to App Data and Files, or more specifically the shared-storage and file-sharing that is a part of App Data and Files is interrupted it will effectively render our app useless.
    
    3. [Google OAuth2.0](https://developers.google.com/assistant/identity/google-sign-in-oauth)
        > This service will be used by our app to keep track of our user base. Furthermore, it will allow us to 


## [Entity Classes](https://github.com/picme-gallery/picme-gallery-service/tree/master/src/main/java/edu/cnm/deepdive/picmegallery/model/entity)
* User
> A user entity class that contains information regarding when a user account was created, the user id key,
>and other Google Oauth login credentials, amongst other things.
  
* Photo
> A photo entity class that contains the location and time-taken photo metadata, as well as, time when a photo is uploaded to the PicMe Gallery Service.
>Additionally, it holds the information regarding which users uploaded which photo, as well as, the info on what event each photo is associated with.

* Event
> An event entity that acts as a _gallery_. It holds the event name, time, location, and password credentials required for
>access to upload photos to a PicMe Event. 

## [Entity-Relationship Diagram](work/entityRelationshipDiagram.md)
    
## [Team Ground Rules](ground-rules.md)