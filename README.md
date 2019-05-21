Flatpicker V4 for Yii2
======================
Flatpicker implementation on Yii2

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist bankwing/yii2-flatpicker "*"
```

or add

```
"bankwing/yii2-flatpicker": "*"
```

to the require section of your `composer.json` file.



## Usage

```php
<?php

use bankwing\Flatpickr\FlatpickrWidget;

?>

<?= $form->field($model, 'published_at')->widget(FlatpickrWidget::class, [
    'locale' => strtolower(substr(Yii::$app->language, 0, 2)),
    // https://chmln.github.io/flatpickr/plugins/
    'plugins' => [
         'confirmDate' => [
               'confirmIcon'=> "<i class='fa fa-check'></i>",
               'confirmText' => 'OK',
               'showAlways' => false,
               'theme' => 'light',
         ],
    ],
    'groupBtnShow' => true,
    'options' => [
        'class' => 'form-control',
    ],
    'clientOptions' => [
        // config options https://chmln.github.io/flatpickr/options/
        'allowInput' => true,
        'defaultDate' => $model->published_at ? date(DATE_ATOM, $model->published_at) : null,
        'enableTime' => true,
        'time_24hr' => true,
    ],
]) ?>
```
