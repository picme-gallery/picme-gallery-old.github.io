## Project Description
Have you ever gone on a trip, or to a party with friends, but forgot to take photos? Or did you forget to ask your friends to send you photos from the event? 
Or have you ever come
home from an event with mostly photos of your friends or acquaintances, but with only a few grainy, questionable selfies of yourself? Are you tired of taking great photos of others, but not having any of your own to show off? Well, fear no more, PicMe Gallery is the app for you.

PicMe Gallery is an app that allows users who are out at an event, or who are traveling together to get access to a secure, cloud-based photo gallery via a shared passkey.

With PicMe in your pocket, you'll no longer have to beg your friends and family to share those photos with you, only to have
them send some mediocre ones where they look good, but you are blinking or look slightly less-than-stellar.

PicMe Gallery's goal is to 
help family and friends seamlessly exchange photos they have of each other through a private-shared gallery that automatically populates from users' phones once an event is underway. Just join the event by entering the event name and password, set your phone to event mode (auto-uploading), and enjoy access to the event gallery for up to three days after the event. After that your photos are deleted from the online gallery, and you get to keep the ones you've downloaded.

No need to mess with iMessage, Messenger, WhatsApp, Facebook, or Google Photos. If you have access to the passkey for the event, just sign in, select your photos, download, and be on your way.

#### Key Functionality

* Automatic uploading of user photos to event gallery, once they're signed in with the event password.
* Camera-integration for ease of photo taking and sharing.
* Android gallery-style selection for intuitive downloading of shared photos.
* Photo captions, metadata, and the username of whomever uploaded the photo, will be available for event documentation and recollection purposes.
* Secure events-based gallery
* Auto-deletion of event info (including user and photo data) after three days for users' security

## [Intended users](work/intendedUsers.md)


## Device & External services
The client component will need access to:
* Device Services
    1. [Native Camera App](https://developer.android.com/training/camera/photobasics)
        > This service will be used by PicMe Gallery to allow our users to upload photos directly from within our app, without having to switch back to the native camera app.
        This service is for convenience. If the service is interrupted, then the users will still be able to upload a photo by taking a picture, and then uploading it from their gallery (i.e. Google Photos, etc.) to PicMe Gallery.
    2. [App Data and Files](https://developer.android.com/guide/topics/data)
        > This service will be used by our app to complete the file-sharing portion of PicMe Gallery's features. It will allow users to save files on their phone.
        Simultaneously, this service will also allow users to share files (photos) to the galleries (events) that are hosted on the server or Web.
        If access to App Data and Files, or more specifically, the shared-storage and file-sharing that is a part of App Data and Files is interrupted, it will effectively render our app useless.
                                                                                
* External Services
    
    3. [Google OAuth2.0](https://developers.google.com/assistant/identity/google-sign-in-oauth)
        > This service will be used by our app to keep track of our user-base. Furthermore, it will allow us to outsource some management of user info to Google.
        Essentially, we will be relying on Google for storing data associated to our users. 
        Without sign-in and authentication through Google services the PicMe Gallery will not be functional. We want to maintain some level of security and credibility over our user-base, while letting Google do the heavy-lifting.



## [Entity Classes](work/entityClasses.md)


## [Entity-Relationship Diagram](work/entityRelationshipDiagram.md)

## Google Sign In
    
