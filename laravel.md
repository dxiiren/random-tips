Situations :
======

## 1) Route not found even have run (php artisan route:list)
- you need to run this
```php
php artisan serve optimize:clear
```

## 2) Save a picture as PDF and print it
- Install Dom PDF
```php
composer require dompdf/dompdf
```

- In Controller
```php
//IN A SIMPLE WAY
$pdf = App::make('dompdf.wrapper');
$pdf->loadView('pages.user-panel.download-pnl', compact('report','consumer'));  //like return view
return $pdf->download('pnl-report' . '.pdf');   //put their name here
// return view('pages.user-panel.download-pnl', compact('report','consumer') );
```

```php
//IN A WAY THE PDF FOLLOW THE PICTURE SIZE
private function makePdf($name,$view,$picture)
{
    $pdf = App::make('dompdf.wrapper');
    $pdf->getDomPDF()->set_option('DOMPDF_ENABLE_AUTOLOAD', false); // Disable autoloading

    list($widthPx, $heightPx) = getimagesize($picture->media->first()->full_url);

    $widthPt =  $widthPx * 0.75 ;
    $heightPt = $heightPx * 0.75 ;

    if($widthPx > $heightPx)
    {
        $orientation = 'potrait';
        $pdf->set_paper(array(0, 0, $widthPt, $heightPt), $orientation);
    }
    else
    {
        $orientation = 'landscape';
        $pdf->set_paper(array(0, 0, $heightPt, $widthPt), $orientation);
    }

    $pdf->loadView($view, compact('picture'));

    return $pdf->download($name . '.pdf');
}
```

```php
//IN VIEW
<!DOCTYPE html>
<html>
<head>
    <title>Receipt View</title>
    <style>
        /* Add your custom CSS styles here */
        html, body {
            margin: 0;
            padding: 0;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .receipt-image {
            max-width: 100%;
            max-height: 100%;
            display: block;
            margin: auto;
        }

        .receipt-iframe {
            width: 100%;
            height: 100%;
            border: none; /* Remove iframe border if needed */
        }
    </style>
</head>
<body>
    <div class="container">
        @if ($picture->media->first()->type === 'pdf')
            <iframe class="receipt-iframe" src="{{ $picture->media[0]->full_url }}"></iframe>
        @else
            <img class="receipt-image" src="{{ $picture->media[0]->full_url }}" alt="Receipt Image">
        @endif
    </div>
</body>
</html>
```

## 3) Try these three commands for clearing cache config:

```php
    php artisan config:cache // clear config cache
    php artisan config:clear // clear config cache
    php artisan cache:clear // clear cache
    php artisan optimize  // To reoptimize the class loader
    php artisan route:cache // clear route cache
    php artisan view:clear // clear view cache
```


