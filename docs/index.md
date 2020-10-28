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
    1. Native Camera App
    2. WiFi and  Network Services
    3. I'm thinking of removing the GPS services, because using a generated key may be similar in functionality, and just as effective.
    4. Access to the native Android Gallery
    5. Google OAuth [Google OAuth2.0](https://developers.google.com/assistant/identity/google-sign-in-oauth)
    6. Potentially may use the [Google ML Kit](https://developers.google.com/ml-kit/vision/face-detection)
    for face detection to sort through the gallery.
    

## Server component

* **Functionality**

    This is where most of the functionality of PicMe will be.
    The server will host a gallery of photos. By utilizing a user registry it will allow users access to that gallery to auto-upload taken photos, and selectively download photos already
    in the gallery. The server will host these photos for only a few days and automatically delete the photos utilizing mySQL delete commands to clear the relational database.

    The server will also authenticate whether or not users have access to a cloud-hosted gallery by comparing the gallery moderator's key and the user-entered
    authentication key to make sure the proper users have access to the gallery. 
    REST-based web services, may be used to GET, POST, PUT, and DELETE shared photos from a gallery, if implementation shifts towards a website platform. 

* **Persistent data**

    Persistent data will include:
    1. Users who have active access to the gallery. (Whomever creates the gallery in the first place will have access to moderate it)
    
    2. User IDs or unique identifiers to each user's OAuth 2.0 account that has access to the gallery. These unique identifiers will have a slot of their own in the server side database which will correspond to an SQL JOINs Query to an ERD, which stores the user taken photos with a unique key-identifier.
    
    3. An array of shared photos, sorted by photo metadata time-stamps. 
    

* **External services**

    I'm currently steering away from integrating preexisting external services; however, there's potential to integrate the app with posting to Instagram, in the future.
    
## Stretch goals/possible enhancements

The implementation of the project on the base level will already be very time-intensive.

However, it would be great to reach the additional goal of implementing a feature that allows posting directly from PicMe's shared gallery to Instagram. In general, the ability to share from a gallery to a post on another platform is what I'm referring to.