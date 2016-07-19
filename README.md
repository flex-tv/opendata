# Flex Open Data

## Open Data Endpoint
https://api.joinflex.tv/v1/open - a feed of the session data from joinflex.tv

## Standards
The data is published to conform to [Openactive Realtime Paged Data Exchange 0.2.3](https://www.openactive.io/realtime-paged-data-exchange/0.2.3/).

## Issues, Questions and Comments
Please raise any issues, questions or comments as a [new issue in this repository](https://github.com/flex-tv/opendata/issues).

## Data Fields

| Field name | Type | Description |
|---|---|---|
| **name** | String | Name of the event (limited to 50 characters). |
| **url** | String | URL of the event. |
| **category** | String | Category of the event (see [categories](#categories) for available values). |
| **description** | String | Description of the event (limited to 200 characters). |
| **image_url** | String | URL of the event image (16:9 aspect ratio). |
| **start_date_time** | ISO8601 String | ISO8601 time representation of the event start date/time. This is expressed as local time with a correct offset from UTC. |
| **duration** | Integer | Duration of the event in minutes. |
| **price** | Decimal | Price of the event in pounds sterling (0 if free). |
| **channel** | Object | 	Object containing information relating to channel responsible for event, as follows: |
| **channel.id** | Integer | Unique ID of the channel. |
| **channel.name** | String | Channel name (limited to 50 characters). |
| **channel.url** | String | 	Channel URL. |
| **channel.tagline** | String | Channel tagline (limited to 70 characters). |
| **channel.description** | String | Channel description (limited to 2000 characters). |
| **channel.location** | String | Channel location (descriptive - not to be relied upon for accurate location-based data) |
| **channel.profile_image_url** | String | URL of the channel profile image (1:1 aspect ratio). |
| **channel.header_image_url** | String | URL of the channel header image (4:1 aspect ratio). |
| **channel.website_url** | String | Channel owner's website URL. |
| **channel.facebook_url** | String | Channel owner's Facebook URL. |
| **channel.twitter_url** | String | Channel owner's Twitter URL. |
| **channel.instagram_url** | String | Channel owner's Instagram URL. |
| **channel.youtube_url** | String | Channel owner's YouTube URL. |
| **channel.intro_video_url** | String | URL of channel introduction video. |
| **created_at** | ISO8601 String | 	ISO8601 timestamp of the date/time the event was created. This is expressed in UTC. |

### Example

```
{
  "name": "Burlexercise - The Ultimate Showgirl Workout",
  "url": "http://www.joinflex.tv/c/burlexercise-the-ultimate-showgirl-workout/events/138",
  "category": "Aerobics",
  "description": "Join us for an all over body workout...with a wiggle! Combining both cardio and resistance, set to a fabulous playlist and with lots of Showgirl sass!",
  "image_url": "https://flex-production.s3.amazonaws.com/uploads/event/image/138/ProfilePic1.png",
  "start_date_time": "2016-07-17T11:00:00+01:00",
  "duration": 30,
  "price": 0,
  "channel": {
    "name": "Burlexercise - The Ultimate Showgirl Workout!",
    "url": "http://www.joinflex.tv/c/burlexercise-the-ultimate-showgirl-workout",
    "description": "Our classes take you on a physical journey, burning calories, toning and tightening all those problem areas from top to bottom, whilst adding some showgirl sass! Our focus is to get you fit, in shape and feeling body confident but most importantly we'll make sure you are having fun exercising!\r\n \r\nWe combine both cardio and resistance for a fabulous all over body workout. All of this is done to Burlesque inspired music from Electro Swing to Showgirl Soundtracks with a few pop diva's thrown in there too!  The great music and fun atmosphere mean you get a class that is energizing and entertaining as well as a good workout!   \r\n \r\nThe creators of Burlexercise have taken inspiration from their careers as London West End dancers, fitness instructors, personal trainers and also professional Burlesque performers to bring you an exercise class like no other!",
    "location": "London",
    "image_url": "https://flex-production.s3.amazonaws.com/uploads/channel/profile_image/29/Burlexercise_tile.png"
  },
  "created_at": "2016-07-07T14:28:58Z"
}
```

### Categories

* Aerobics
* Bodybuilding
* Bootcamp
* Dance
* HIIT
* Indoor Cycling
* Martial arts
* Meditation
* Pilates
* Sports
* Yoga
* Zumba
* Other

### Note

Section [4.4 Related entities](https://www.openactive.io/realtime-paged-data-exchange/#related-entities) of the Openactive Realtime Paged Data Exchange specification specifies that updates to nested entities (i.e. channel) be reflected in the item modified timestamp. Currently this implementation does not meet this requirement. Sessions, however, are the time-critical data and channel data is expected to see irregular updates. Consumers subscribed to the [mailing list](http://data.joinflex.tv/) will be notified upon the update of this implementation regarding this.

## Changelog

| Date | Changes |
|---|---|
| 17/07/2016 | Initial version published |
