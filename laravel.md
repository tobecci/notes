# LARAVEL NOTES

* this note is divided into sections

## BLADES

* in the file containing the header and footer, do `@yield('content')` in any portion of code
* in the file that you want to display in the section, at the to do `@extends('file_name')` and do `@section('content') content of the page goes here @endsection`

## ARTISAN

* `php artisan help <command>` gives information about how to use that command

## CONTROLLERS

* return a view by doing so 
```php
public function index(){
	return view('viewName');
}
``` 

## ROUTES