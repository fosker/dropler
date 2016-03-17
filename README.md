# УСТАНОВКА

Хуячишь в проект папку dropler. Во вьюхе, в которой собираешься это дерьмо юзать, в самом верху ебошишь следующее: 
```php
$this->registerJs("CKEDITOR.plugins.addExternal('dropler','".Yii::getAlias('@web')."/js/ckeditor/plugins/dropler/');");
```

Далее подключаешь плагин через ```extraPlugin``` и указываешь в конфиге ```uploadUrl```, который обрабатывает загрузку файлов.
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
                    'uploadUrl' => 'http://farm.loc/backend/components/upload.php'
                ]
            ]
        ],
        'preset' => 'basic',
    ]); ?>
```