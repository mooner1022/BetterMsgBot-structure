<h1 align="center">📜<br>ChatBot-structure</h1>

<p align="center">
This documentation defines common API structure used in
<br>'BetterMsgBot' and `Project StarLight`
</p>

> **Note**: This structure is still under development. If there is a structure you want, please put pr without any worries.

### Structure specification
+ All `core API`s and `extension API`s are packaged in several classes
which can recognise its usage, not in one Api class
    + ex)
    + `Projects.get(projectName);`
    + `Timer.schedule(duration, callback);`

+ Uses `EventEmitter` method instead of `Function-based` method used in
`API1`. Indicating as `BotClient` below in order of convenience.
> Restricted in `Project StarLight`, `EventEmitter` class offers
> extension support for plugins.

+ Defines an executable programming language object as `Language`
+ Defines unit for a bot instance as `Project`
    + `Project` class contains bot configuration and compiled `engine` object

### Core API
+ `BotClient`
    + `EventEmitter` typed event listener method
    + Uses event type to register listener callback, which is described below
        + `on(eventType, callBack)`
            + Register event listener matching `eventType`
          ####
        + `once(eventType, callBack)`
            + Register event listener *called only once* matching `eventType`

### Extension API
+ `Languages`
    + Return object for specific language
        + `get()`
            + Return the language used in current project
        + `get(languageId)`
            + Return the language which has `languageId` as its id,
          returns `null` if not exists
####
+ `Projects`
    + return object for specific project
        + `get()`
        + Return current project
        + `get(projectName)`
            + Return project named `projectName`, returns `null` if not exists
####
+ `Timer`
    + Set timer which works asynchronously
        + `schedule(delay, callback)`
            + Run `callback` after `delay` (expressed in millisecond)
            + Returns `java.util.Timer`
      ####
        + `schedule(initialDelay, period, callback)`
            + Run `callback` every `period` after `initialDelay` (expressed in millisecond)
            + Returns `java.util.Timer`

###### /* To be continued.. */

### Event types
+ Default event types which can be used on `BotClient`
+ [SpreadSheet document](https://docs.google.com/spreadsheets/d/103k-cqYOIrk9ZpHiu1ZbEKqFNTkxnJXrrPJKfLvxUlY)

