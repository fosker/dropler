# ���������

������� � ������ ����� dropler. �� �����, � ������� ����������� ��� ������ �����, � ����� ����� ������� ���������: 
```php
$this->registerJs("CKEDITOR.plugins.addExternal('dropler','".Yii::getAlias('@web')."/js/ckeditor/plugins/dropler/');");
```

����� ����������� ������ ����� ```extraPlugin``` � ���������� � ������� ```uploadUrl```, ������� ������������ �������� ������.
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