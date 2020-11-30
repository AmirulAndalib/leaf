<!-- markdownlint-disable no-duplicate-header -->
# Changelog

## v2.4.0 - BETA - 30th November, 2020

Unlike previous versions, this version of Leaf is focusing on improving the use of existing features, rather than just pumping new magic into Leaf. It has a lot of bug fixes, standardization of method names and overall upgrades.

### Added

- Added `App::evadeCors`
- Added `App::routes` to preview all routes
- Added `Db::first()`
- Leaf DB can now detect query type even when `query`
- Added `orWhere`, `whereLike`, `orWhereLike` `like`, `orLike`, `orderBy`, `all` `limit` and LIKE helpers to Leaf Db
- Added new format to `Date::now`
- Added `Auth::update`
- Added custom token lifetime support on `Auth`

### Fixed

- Fixed login bug with `Auth::currentUser`
- Fixed Leaf DB same value bug
- Minor fixes on `Auth::login` and `Auth::register`

### Changed

- Switched methods to camel case
- Renamed `Auth::useToken` to `Auth::id`
- Renamed `Auth::currentUser` to `Auth::user`
- Made `Helpers\JWT` and `Helpers\Authentication` methods static

### Removed

- Removed `Form::isEmpty` and `Form::isNull`
- Removed deprecated methods from `Response`
- Removed deprecated methods from `Date`

## v2.1.0 - 19th June, 2020

### Added

- Added `Leaf\Auth::auto_connect`
- Added default bypass for CORS errors
- Added `Mysqli::auto_connect`
- Added optional `db_type` option to `Leaf\Db\PDO` connection
- Added `PDO::auto_connect`
- Added deprecation warning for `Leaf\Db\PDO`

### Fixed

### Changed

### Removed

- Removed Leaf\Wynter

## v2.1.0 - alpha - 24th May, 2020

### Added

- Added Route::resource
- Added Session::retrieve

### Fixed

### Changed

- Seperated Leaf Veins from Leaf Package
- Renamed Session::getBody to Session::body

### Removed

- Removed Leaf\View

## v2.0 - official - 21st April, 2020

### Added

- Added Leaf Mail
- Added Date::days_ago
- Added Date::months_ago
- Added Date::years_ago
- Added Date::day
- Added Date::month
- Added Date::year
- Added Auth::setSecretKey
- Added Auth::getSecretKey
- Added Auth::validate
- Added Leaf JS Scripts [BETA]
- Added Leaf Envryption Helper [BETA]
- Added Leaf Password Helper [BETA]
- Added secret key for token encryption in Leaf Authentication

### Fixed

- Fixed Request::params
- Fixed Request::getBody
- Fixed Request Method Tests
- Fixes to Auth::validateToken
- Fixed bugs with Leaf DB packages
- Fixed bugs on Auth::login and register
- Fixed base64 security issues on Leaf Token [BETA]
- Fixes on Form::isEmpty and isNull

### Changed

- Renamed Request `getBody` to `body`
- Switched all `Date` methods to `snake_case`
- Switched `FS` methods to `snake_case`
- Shortened `Date` method names (Find out more in the [docs](https://leafphp.netlify.com/))
- Made Leaf Authentication a helper (Leaf\Helper\Authentication)

### Removed

- Removed Response::count
- Removed Response::getIterator
- Removed Response header offeset methods

## v2.0 - beta - 11th March, 2020

### Added

- Added DB->choose
- Added DB->add
- Added Auth->login
- Added Auth->register
- Added Session->unset
- Added custom constructor to response
- Added Response->messages(Http codes)
- Added Response->setStatus/getStatus/status
- Added Response->setHeader/getHeader/header
- Added Response->setCookie/deleteCookie
- Added Response->redirect
- Added Request type checks
- Added Request->cookies
- Added Request->headers
- Added Response Helpers
- Added Leaf\Headers
- Added Leaf\Cookies
- Added ContentTypes Middleware
- Added Flash messaging Middleware
- Added PrettyExceptions Middleware
- Added Logwriter and Log
- Added Leaf View
- Merged the Leaf Veins Templating engine and Leaf Core
- Added Support for blade templating with Leaf Blade
- Added support for more request types on Leaf::Request
- Added Form::validateField
- Provided security against XSS
- Added Form::submit

### Fixed

- Fixed SESSION->id
- Fixed headers bug with Response->respondWithCode
- Fixed headers bug with Response->throwErr

### Changed

- Changed Leaf\Core namespace to Leaf
- Changed Session->remove to Session->unset

### Removed

- Removed Auth->basicLogin
- Removed Auth->emailLogin
- Removed Auth->basicRegister

## v1.5.0 - 11th December, 2019

### Added

- Added FS->deleteFolder
- Added FS->deleteFile
- Added Form->validate😅
- Added Form->validate and return errors to base controllers
- Added Leaf\Core\Str: equivalent of Illuminate\Support\Str with added methods
- Added Leaf Mysqli🤔
- Added Leaf PDO🤔
- Added Leaf\Core\Auth: simple login and signup

### Fixed

- Fixed FS->deleteFile
- Fixed FS->listDir
- Fixed Leaf DB
- Fixed init bug with session

### Changed

- Renamed Veins->renderTemplate to render
- Rename veins->assign to set()
- Renamed mkdir to createFolder
- Renamed mkdirInBase to createFolderInBase
- Renamed renameDir to renameFolder
- Changed vein file extension from .vein to .vein.php
- Split Leaf\Config\Db between Leaf\Core\Db\Mysqli and Leaf\Core\Db\PDO
- Changed `renderHtml` to `renderPage`
- Changed all `getParam`s to `get`

### Removed

Nothing was removed

## v1.4.2 - 13th November, 2019

### Added

- Added FileSystem module
- Added `mysqliQuery` method to `leaf\config\db`
- Added a bunch of handy session methods
- Added leaf token
- Added leaf form

### Fixed

- Fixed  a few problems with `leaf\config\db`;
- Fixed tiny bug with `response->throwErr`

### Changed

- Changed `leaf\config\db`: connection variables and connection type are set on db init. `$db = new db($host, $user, $password, $dbname, "PDO")`
- Renamed renderHtmlPage to renderHtml

### Removed

- Leaf\Config\DB has been depricated for now

## v1.4.1 - 1st November, 2019

### Added

- Added base Leaf Controller `Leaf\Core\Controller`
- Added base controller for APIs: `Leaf\Core\ApiController`
- Added base Leaf Model `Leaf\Core\Model`
- Added support for full MVC app
- Added [Leaf Veins](https://github.com/leafsphp/veins) in default Leaf package
- Added Error Handling for development and production
- Added a base database layer connected with custom environment variables

### Fixed

- Fixed bug with `Response::renderHtmlPage()`
- Fixed the HTTP code rendering in the browser from `Response::respondWithCode`

### Changed

- Changed `Validation` to `Form`

### Removed

- Removed Leaf `Exceptions`
- Removed Middleware interfaces
