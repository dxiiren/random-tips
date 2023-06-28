Situations :
======

## 1-Route not found even have run (php artisan route:list)
- you need to run this
```php
php artisan serve optimize:clear
```


## 2-Save a picture as PDF and print it
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

