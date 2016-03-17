# Install

Create a folder named ```dropler``` in your project directory. In view file where you gonna use this shit at start of file write next:
```php
$this->registerJs("CKEDITOR.plugins.addExternal('dropler','".Yii::getAlias('@web')."/js/ckeditor/plugins/dropler/');");
```

Next you should add ```dropler``` plugin by using ```extraPlugin``` in the widget. Also you need to specify ```uploadUrl``` which will process uploading on your server.
```php
<?= $form->field($model, 'description')->widget(Editor::className(), [
        'options' => [
            'rows' => 6,
        ],
        'clientOptions' => [
            'extraPlugins' => 'dropler',
            'droplerConfig' => [
                'backend' => 'basic',
                'settings' => [
                    'uploadUrl' => 'upload.php'
                ]
            ]
        ],
        'preset' => 'basic',
    ]); ?>
```