# Local Storage 

## THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS 

***ersistent local storage is one of the areas where native client applications have held an advantage over web applications. For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files, or some other place according to platform convention. If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.*** 

***web applications have had none of these luxuries. Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:*** 

* Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over

* Cookies are included with every HTTP request, thereby sending data unencrypted over the internet

* Cookies are limited to about 4 KB of data — enough to slow down your application, but not enough to be terribly useful 

> A BRIEF HISTORY OF LOCAL STORAGE HACKS BEFORE HTML5 

**In the beginning, there was only Internet Explorer. Or at least, that’s what Microsoft wanted the world to think. To that end, as part of the First Great Browser Wars, Microsoft invented a great many things and included them in their browser-to-end-all-browser-wars, Internet Explorer. One of these things was called DHTML Behaviors, and one of these behaviors was called userData.** 

> userData 

**allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure. IE does not present any form of permissions dialog, and there is no allowance for increasing the amount of storage available.** 

> INTRODUCING HTML5 STORAGE 

**“HTML5 Storage” is a specification named Web Storage, which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons.** 

> So what is HTML5 Storage ?

*it’s a way for web pages to store named key/value pairs locally, within the client web browser.** 

> USING HTML5 STORAGE 

**HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.**

interface Storage {

  getter any getItem(in DOMString key);

  setter creator void setItem(in DOMString key, in any data);

};

> TRACKING CHANGES TO THE HTML5 STORAGE AREA 

**The storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and actually changes something.**

if (window.addEventListener) {

  window.addEventListener("storage", handle_storage, false);

} else {

  window.attachEvent("onstorage", handle_storage);

};

> HTML5 STORAGE IN ACTION 

**HTML5 Storage can save the progress locally, within the browser itself. Here is a live demonstration. Make a few moves, then close the browser tab, then re-open it. If your browser supports HTML5 Storage, the demonstration page should magically remember your exact position** 

> BEYOND NAMED KEY-VALUE PAIRS: COMPETING VISIONS 

**the present condition of HTML5 Storage is surprisingly rosy. A new API has been standardized and implemented across all major browsers, platforms, and devices.** 

**One vision is an acronym that you probably know already: SQL. In 2007, Google launched Gears, an open source cross-browser plugin which included an embedded database based on SQLite. This early prototype later influenced the creation of the Web SQL Database specification. Web SQL Database (formerly known as “WebDB”) provides a thin wrapper around a SQL database,**