## Laravel Akismet

### Installation
Install this package with composer:
```
php composer.phar require nickurt/laravel-akismet:dev-master
```

Add the provider to config/app.php file

```
'nickurt\Akismet\ServiceProvider',
```

and the facade in the file

```
'Akismet' => 'nickurt\Akismet\Facade',
```

Copy the config files for the api

```
php artisan vendor:publish
```

### Examples
#### Validate Key
```php
if( \Akismet::validateKey() ) 
{
    // valid
}
else 
{
    // invalid
}
```
#### Set CommentAuthor Information
```php
\Akismet::setCommentAuthor("John Doe")
    ->setCommentAuthorUrl("https://www.google.com")
    ->setCommentContent("It's me, John!")
    ->setCommentType('registration');
    // etc
    
// or
\Akismet::setCommentAuthor("John Doe");
\Akismet::setCommentAuthorUrl("https://www.google.com");
\Akismet::setCommentContent("It's me, John!");
// etc
```
#### Get CommentAuthor Information
```php
if( \Akismet::getCommentAuthor() == 'John Doe' )
{
    // it's me John!
}
```
#### isSpam?
```php
if( \Akismet::isSpam() )
{
    // yes, i'm spam!
}
```
- - - 