## Laravel Web Push Example

A basic example of using webpush notifications with laravel and Javascript. Push Notifications are a part of Service Workers and It requires HTTPS unless you are using localhost.

#### Running this web application

-make sure you have xampp or wamp installed if you are on windows machine, mamp for mac , and lamp for linux.

-clone this repository to your local machine or just download the zip.

-install Composer first, then run this command in your command-line (you should be inside your project directory).

  `composer install`
-rename .env.example to .env and configure your database.

-generate application key.

    `php artisan key:generate`
-create tables by migrations.

    `php artisan migrate`
    
-Generate VAPID Keys (this command will place the VAPID keys in your .env file).

    `php artisan webpush:vapid`
    
-Add the VAPID public key to application server key in enable-push.js file located in public/js directory, here's the link to that line

To make build

 `npm install`

  `npm run build`

-Start Laravel dev server.

    `php artisan serve`

Read the entire tutorial Push Notifications with Laravel and Webpush on Medium.

Webpush package is used by this app.
---------------------------------------------------------------------------------------
### Laravel (PWA) Progressive Web Aplication

This Laravel pakage turns your project into a progressive web app. 

Launching the app from your home screen will display your app. As such, it's critical that your application provides all navigation within the HTML (no reliance on the browser back or forward button).

### Requirements
Progressive Web Apps require HTTPS unless being served from localhost. 

### Installation
Add the following to your composer.json file :

"require": {
    "silviolleite/laravelpwa": "~2.0.3",
},

or execute

composer require silviolleite/laravelpwa --prefer-dist

Publish

php artisan vendor:publish --provider="LaravelPWA\Providers\LaravelPWAServiceProvid"
### Installation

Configure your app name, description, icons and splashes in config/laravelpwa.php.

Include within your <head> the blade directive @laravelPWA.

    '<html>
    <head>
        <title>My Title</title>
        ...
        @laravelPWA
    </head>
    <body>
        ...
        My content
        ...
    </body>
    </html>'
This should include the appropriate meta tags, the link to manifest.json and the serviceworker script.

### Troubleshooting

While running the Laravel test server:

Verify that /manifest.json is being served
Verify that /serviceworker.js is being served
Use the Application tab in the Chrome Developer Tools to verify the progressive web app is configured correctly.
Use the "Add to homescreen" link on the Application Tab to verify you can add the app successfully.

