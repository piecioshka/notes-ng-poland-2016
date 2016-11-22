# notes-ng-poland-2016

:book: Notes from conference: ng-poland 2016

## 1. "Server-side rendering with Angular 2" Wassim Chegham

* @manekinekko
* Google Developer Expert
* http://slides.com/wassimchegham/angular2-universal
    - świetne slajdy
    - duże fonty
    - kafelki łączą się przez trójkąt
    - delikatne animacje pojawiających się kafelków

---

### Why should we care SSR? SEO

### Dlaczego "link preview" działa np. na Facebook-u

* bo jest SSR (Server-side rendering)
* jeśli by nie było to byłaby pusta strona

### Web App Gap

#### How to improve tti? (time to interactive)

* user start interact with your app

#### Ng 2 app
#### app layer
#### rendering layer

* server - node
* web workers
* browser

`preboot.js`

**Nigdy nie dotykać DOMa, tylko `renderer.setElemtnyStyle()`**

#### GitHub: angular/universal-start

#### AoT suport

> wkrótce angular-cli będzie wspierał --universal

#### ng docs - static docs generator

http://ng-bootstrap.github.io

* now render server-side with angular-universal
* @pkozlowski_os
* http://mobile.angular.io
* http://universal.angular.io

## 2. "Using Angular CLI to deploy an Angular 2 App Using Firebase in 30 minutes" Tracy Lee

* medium.com/@ladyleet
* github.com/@ladyleet
* twitter.com/@ladyleet
* http://modern-web.org
* http://www.slideshare.net/ladyleet/using-angularcli-to-deploy-an-angular-2-app-using-firebase-in-30-minutes

---

#### Short list of awesome

* tree shaking
* route generation

**ng-cruise - konferencja na Bahamach?**

#### Create ang-cli ng2 app

```
npm i -g angular-cli@latest
ng new <name>
ng s
```

#### materialize-css

```
npm i materliaze.css
index.html add 3 files
google roboto font
```

#### ng ng-cli app structure

```
app.component.ts - man application component
app.module.ts
```

#### creating components

```
ng gnerate <component name>
ng g --help fo full list
ng g c -is -it --no-spec <componnet-name>
```

#### Live coding!!

> material-css ma ładne domyślne style

#### Using the new router

#### Template driven form

#### Deploying to firebase.google.com

```
npm i -g firebase-tools
firebase login 
ng build
firebase init
> piękny wizard
firebase deploy
```

## 3. "Angular 2, of Things" Uri Shaked

* media.com/@urish
* Google Developer Experts for Web Technologies

---

* Nie będzie slajdów, tylko sam kod!
* Będziemy omawiali grę
* **Chrome Extension: Augury**
* Celem prelekcji jest uruchomienie aplikacji simon na Raspberry PI
* Podczas prelekcji z użyciem hardware-u wszystko może pójść źle.

> świetna prelekcja, tonacja głosu, wszystko zgodnie z planem

http://ngconf-simon.firebsaseio.com

## 4. "Angular 2 and WebSockets" Adam Nowaczyk (Platinium Sponsor - Acaisoft)

Simple quiz Angular2 base on AWS IoT platform over WebSocket and MQTT

### Clients

* login thi custom nick
* get questions to answer

### Presentation/server

* preview of logged users, questions and answers
* state management (the brains)

https://acaisoft.mobi

### Nie martwimy się skalowalnością.

Każdy z nas może postawić serwer w Node.js dla 20 userów,
ale coś jeśli tych użytkowników będzie milion?

http://aws.amazon.com

### Key challengers

* getting websocket enabled backend
* deciding on the message queue protocol (mqtt.js)
* binding it together with angular2
* switching form system.js to webpack
* plugin material design as angular2 components
* choosing right data/state flow pattern
* gettings benefits of rxjs stuff

Stream-y mają to do siebie, że nie kończą swojego działania po wykonaniu się,
tak jak ma to miejsce w przypadku promisów

http://github.com/ngrx/store

### Lesson learn (pros)

* websockets are cool - hoverwer not alone you want to user 1 connection and 
route message over it MQTT FTW! Alternative would be to go with STOMP or AMQP
* aws lot is cool - really interesting platform, with all the builds in 
routing possibilities and aws services integration make it worth considering 
for production ready - scalable solutions
* angular 2 is cool - project developed by 6 overtime developers PRs worked 
great, nice separation of responsibilities acesoss the code
* we will definitely check redux (ngrx/store) as command based unidirectional
 state management looks promising

### Lesson learned (cons)

* material design support for angular2 is still poop
* our webpack configuration sux - we must fix it - probably angular-cli tis
the way to go
* we haven't managed to use ngrx/store for our state management , but ont he 
other hand came up with our own simplified version
* haven't managed to implement nice clean d3 based charts
* missing tests - no excuse for that
* newbie approach to rxjs - it's great stuff and we'd like eto dive deeper. 
Try "everything is stream" approach really make sens on backend
* there's always not enough time

## 5. "Why it pays to know AngularJS?" Paweł Zdziech (Silver Sponsor - 7N)

* 10 minutes talk
* http://rekrutacyjny.blogspot.com

---

"The man who graduates today and stops learning tomorrow is uneducated the day after"
 
newton d. baker (1871 - 1937)

## 6. "An empty database in everybody's pocket" Phil Nash

* @philnash
* http://philna.sh
* https://speakerdeck.com/philnash/an-empty-database-in-everybodys-pocket-at-ng-poland

---

* Performance
* Offline (or poor connectivity {of resiliency})
* User experience

### WebSQL is dead

### IndexDB

* object store
* transactional
* asynchronous
* same origin policy (any javascripts)

### DEMO!

### Libraries

* idb-keyval
* localForage
* idb
* Dexie
* PouchDB

Similar projects:

* angular2-indexeddb
* angular-indexedDB

## 7. "Angular and Redux in practice" Nir Kaufman

If you are building CRUD application.
Today we building dashboard.

* Single source of truth

```javascript
const state = {
    tabs: [],
    account: [],
    sidebar: {}
}
```

* The state is READ ONLY

**Chrome Extension: Redux**

## 8. "The amazing Angular 2 Router" Gerard Sans

* Master of ceremonies
* http://slides.com/gerardsans
* Community Leader (Angular Zone - in London)

---

### Features

* latest web standards
* great developer experience
* simple

http://angularexpo.com

### Requirements

* network resilience
* ask before navigating
* restrict access
* lazy loading

```javascript
this.http.get()
    .map(/* ... */)
    .retryWhen(/* ... */)
```

### Router - main features

* url-based navigation
* flexible routing
    - child and auxiliary routes
* navigation guards
* lazy loading and preloading
* resolve

### Setup router

### Dependencies

* choose location strategy
* setup routes
* include providers and directives

    ```
    RouterModule.forRoot(routes)
    RouterModule.forChild(routes)
    ```

```javascript
router.navigate(['user', 34]);
router.navigateByUrl('/user/34');
```

## 9. "RxJS 5 in Modern Web Applications" Ben Lesh

## 10. "The legend of ngModules" Shai Rzeznik

* @shai_rznik
* hirez.io
* ng-wat
* świetnie wytłumaczone o co kaman w modułach na podstawie historii chomika
* slajdy z kodem, gdzie komentarze są żółtym fontem (podobnym do pisanego)

---

### app-module

* component
* service
* pipe (stare filtry)
* directive

### providers - belongs injector

* service1 
* service2

### declarations - belongs compiles

* components
* pipe
* directives

### Feature modules

* split by functionality

### Examples 

* FRONT PAGE
* LOGIN PAGE

### We didn't cover

* shared modules - dry
* core modules - services and core
* never declare services on lazy loaded and shared modules

### Summary

* must have at least 1 root module
* sub divide yur features
* import only exported declarations
* services are added to the app injector

## 11. "Progressive Angular 2 apps" Ciro Nunes

* @cironunesdev
* Google Developer Experts

---

* discoverable
* installable
* responsive
* linkable
* connectivable

1. Web Application Manifest
2. Application shell
    - architect & implement your app shell
    - cache via service workers
3. Cache (SW)

## 12. "Angular 2 styel guide" Alex Lakatos

* @lokatos88

---

### Single responsibility

* do define one thing per file
* consider limiting files to 400 lines of code
* do define small function
* consider limiting to no more that 75 lines

### Naming

* do use consistence names for all symbols
* do follow a pattern that describes the symbols feature then is type
(feature.type.ts)
* do use dashes to separate words in the descriptible name
* do try to stick with conventional type names, service, component, pipa, 

## 13. "ng-enterprise" Tomasz Ducin

* @tomasz_ducin
* http://slides.com/ducin/ng-enterprise

---

### Architecture

* how the app is structured
* the toolstack used
* all the design decisions you have to make before coding
    - why
    - how
    - what

### A remake (new version of existing app)

* re-implement everything
* implement top 10 features, deliver 2 parallel apps
* make old 7 new co-exist within 1 system

### Directive

* originally reusable piecie of logic
* need to define
    - the relationships
    - responsibility
    - communication
    
### When to make Decisions?

* as soon as you know
* as late as possible
* each decision reduces flexibility
* each change costs
* each bad decision costs a LOT

### JS Fatige

> don't focus on tools, instead think's about the problems you solve

* budget-driven develpment
* big, distributed teams
* backends being unavailable
* BE changes force FU changes
* BE needs to be implemented prior to FE

### $httpBackend

Frontend first development - Backend-less approach

* 90% actual development 
* 10% FE - BE sync

### Performance - Digest Cycle

### Future

* remake is a big investment
* how about angular 2?

### Remember

* **don't focus on tools, focus on the problem**

## 14. "The future of Angular client-server communication with GraphQL" Uri Goldstein

* @unigoldshtein
* dev.apollodata.com

---

GraphQL jest lepszy niż REST.

## 15. "Building a robot app with NativeScript" Sebastian Witalec

* @sebawita

---

* NS to nie jest Cordoba
* NS nie korzysta z DOMa
* NS używa natywnych kontrolek, dlatego jest szybki
* Direct access to native APIs in JS
