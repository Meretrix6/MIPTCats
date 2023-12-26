# MIPTCats
Team 11(MIPTCats) HW

# Тема работы
Прогнозирование погоды с использованием методов машинного обучения.

# Участники:
 	
Ильиных Александр Александрович
Зайцев Дмитрий Витальевич 	
Гриднев Константин Александрович
Самаковский Вячеслав Олегович
Алиева Наталья Геннадьевна

# Файлы:

CatsRoboflow.ipynb - модель Roboflow

Cats_tenserflow.ipynb - модель tenserflow

Presentation_MIPT_cats_v1.pdf - Презентация

## Оглавление
[1. Описание программы](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Описание-дз)

[2. Условия задачи](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Условия-задачи)

[3. Способ решения](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Способ-решения)

[4. Выводы](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Выводы)


### Описание программы
По полученной фотографии определяет погоду (туман, мороз, молния, дождь, радуга, песчанная буря, снег, солнечно)

:arrow_up:[к оглавлению](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Оглавление)

### Условия задачи
1) Сделать датасет для классификации погоды по выбранным классам.
2) Обучение модели
3) Проверка модели на тестовых данных
4) Сравнение обученной модели с уже существующей    

:arrow_up:[к оглавлению](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Оглавление)

### Способ решения
Для выполнения данной задачи был выбран датасет - https://drive.google.com/drive/folders/1s06Vvw0NVJLWO23LKrYqbDtIVFaEsHDq, на его основе была обучена нейросеть в облаке с помощью roboflow и tensorflow. 

:arrow_up:[к оглавлению](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Оглавление)

### Выводы
Были обучены две модели, одна на Roboflow вторая на tenserflow. Модель Roboflow была сравнена с существующей моделью Roboflow на трех тестовых изображениях. Точность модели tenserflow была сравнена с нашей моделью на Roboflow

1) Первое изображение, признак, который принадлежит к обеим моделям.
    Было выбрано изображение с дождем, наша модель ('rain': {'confidence': 0.9434818029403687}) справилась хуже чем, существующая модель('Rain', 'confidence': 0.9999). Связанно это с тем, что наша модель поддерживает болшее количество признаков, и с размером дата_сетов для обучения.

2) Второе изображение, содержало в себе 2 признака.
    Изображение содержало в себе дождь с радугой. Наша модель ('rain': {'confidence': 0.42170989513397217}, 'rainbow': {'confidence': 0.47663456201553345}) отлично справилась с поставленной задачей, существующая модель ('class': 'Rain', 'confidence': 0.9995) определила только дождь без радуги. Это связано с тем что модель которою мы сделали обучалась на большем количестве признаков.

3) Третье изображение содержало в себе признак, которого нет в существующей модели.
    Изображение содержало в себе молнию. Так как был выбран признак, которого нет в другой модели({'class': 'Shine', 'confidence': 0.9841}), ожидаемо наша модель ('lightning': {'confidence': 0.9249942898750305}) ее превзошла.

Большее количество признаков требует больше данных для анализа, что повышает качество обученной модели.

Validation Accuracy
tensorflow = 0.97
roboflow = 0.98

Обученная модель tensorflow весила больше 100 Мб https://disk.yandex.ru/d/a3n_0C3_H5QJhA

:arrow_up:[к оглавлению](https://github.com/Meretrix6/MIPTCats/tree/main/README.md/#Оглавление)