# Wstęp do JavaScript

Dlaczego JavaScript jest wyjątkowy? Co możemy zrobić dzięki JavaScript i pokrewnym technologiom? Aby się tego dowiedzieć czytaj dalej.

## Czym jest JavaScript?

*JavaScript* początkowo był stworzony aby *"ożywić strony internetowe"*.

Programy napisane w tym języku są nazywane *skryptami*. Mogą być pisane wewnątrz kodu HTML i wykonywane są automatycznie po odświeżeniu strony.

Skrypty to zwykły tekst. Nie wymagają specjalnego przygotowania czy kompilacji przed uruchomieniem.

Pod tym względem, JavaScript bardzo różni się od innego, bardzo popularnego języka  [Java](http://en.wikipedia.org/wiki/Java)

```smart header="Why <u>Java</u>Script?"
Gdy tworzono JavaScript, nadano mu nazwę "LiveScript". Jednak w tym czasie Java była bardzo popularnym językiem, dlatego zdecydowano promować JavaScript jako młodszego brata Javy, z nadzieją na szybsze wybicie się z nowym produktem na rynku.

JavaScript szybko ewoluował i rozwijał się. Wkrótce stał się całkowicie niezależnym językiem, ze swoją własną specyfikacją nazwaną [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) i obecnie nie ma absolutnie żadnych powiązań z Javą.
```

Obecnie, skrypty JavaScript mogą być wykonywane także poza przeglądarką. Po stronie serwera lub na każdym innym urządzeniu wyposażonym w tak zwany [Silnik Javascript](https://en.wikipedia.org/wiki/JavaScript_engine).

Przeglądarki mają osadzone silniki, czasem nazywane "Wirtualną Maszyną JavaScript"

Różne silniki mają różne nazwy, np:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- występuje w Chrome i Operze.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- występuje w Firefox.
- ...a także inne pod nazwami takimi jak "Trident", "Chakra" przeznaczone dla różnych wersji Internet Explorer, "ChakraCore" dla Edge, "Nitro" i "SquirrelFish" dla Safari itp.

Pojęcia użyte powyżej warto zapamiętać, ponieważ są często używane przez developerów w artykułach czy tekstach w internecie. W tej książce także będą używane. Na przykład, jeśli "właściwość X jest obsługiwana przez V8", prawdopodobnie będzie działała w przeglądarce Chrome i Opera.


```smart header="How engines work?"
Silniki są skomplikowane. Jednak założenia działania bardzo proste.

1. Silnik (wbudowany, jeśli mówimy o przeglądarce) czyta ("parsuje") skrypt.
2. Następnie konwertuje ("kompiluje") treść skryptu na język maszynowy.
3. I w tej chwili skrypt może zostać uruchomiony.

W silnikach stosuje się optymalizację na każdym poziomie tego procesu. Obserwują one działające skrypty, analizują dane i na ich podstawie wykonują kod najlepiej i najszybciej jak to możliwe.
```

## What can in-browser JavaScript do?

The modern JavaScript is a "safe" programming language. It does not provide low-level access to memory or CPU, because it was initially created for browsers which do not require it.

The capabilities greatly depend on the environment that runs JavaScript. For instance, [Node.JS](https://wikipedia.org/wiki/Node.js) supports functions that allow JavaScript to read/write arbitrary files, perform network requests etc.

In-browser JavaScript can do everything related to webpage manipulation, interaction with the user and the webserver.

For instance, in-browser JavaScript is able to:

- Add new HTML to the page, change the existing content, modify styles.
- React to user actions, run on mouse clicks, pointer movements, key presses.
- Send requests over the network to remote servers, download and upload files (so-called [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) and [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) technologies).
- Get and set cookies, ask questions to the visitor, show messages.
- Remember the data on the client-side ("local storage").

## What CAN'T in-browser JavaScript do?

JavaScript's abilities in the browser are limited for the sake of the user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.

The examples of such restrictions are:

- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS system functions.

    Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like "dropping" a file into a browser window or selecting it via an `<input>` tag.

    There are ways to interact with camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must contain a special JavaScript code that handles data exchange.

    The limitation is again for user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com` and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's safety limitations.

![](limitations.png)

Such limits do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow installing plugin/extensions which may get extended permissions.

## What makes JavaScript unique?

There are at least *three* great things about JavaScript:

```compare
+ Full integration with HTML/CSS.
+ Simple things done simply.
+ Supported by all major browsers and enabled by default.
```

Combined, these three things exist only in JavaScript and no other browser technology.

That's what makes JavaScript unique. That's why it's the most widespread tool to create browser interfaces.

While planning to learn a new technology, it's beneficial to check its perspectives. So let's move on to the modern trends that include new languages and browser abilities.


## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and autoconverting it "under the hood".

Examples of such languages:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript, it introduces shorter syntax, allowing to write more precise and clear code. Usually Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing", to simplify development and support of complex systems. It is developed by Microsoft.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps). It was initially offered by Google as a replacement for JavaScript, but as of now, browsers require it to be transpiled to JavaScript just like the ones above.

There are more. Of course even if we use one of those languages, we should also know JavaScript, to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but now it is used in many other environments as well.
- At this moment, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
