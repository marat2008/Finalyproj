## Тип моего проекта:
> мемы

## Библиотеки, которые я буду использовать
-Flask
## Референсы, которые мне пригодятся
- https://www.meme-arsenal.com/create/chose

## Гайды-статьи, где есть полезная для меня информация
(https://cyberleninka.ru/article/n/sozdanie-mema-kak-sotsiokommunikativnaya-tehnologiya-v-mediaprostranstve)
 
#Импорт
from flask import Flask, render_template, request, send_from_directory


app = Flask(__name__)

#Результаты формы
@app.route('/', methods=['GET','POST'])
def index():
    if request.method == 'POST':
        # получаем выбранное изображение
        selected_image = request.form.get('image-selector')
        return render_template('index.html', 
                               # отображаем выбранное изображение
                               selected_image=selected_image, 

                               # Задание №2. Отображаем текст
                               

                               # Задание №3. Отображаем цвет 
                               
                               
                               #Задание №3. Отоброжаем расположение текста

                               )
    else:
        # отображаем первое изображение по умолчанию
        return render_template('index.html', selected_image='logo.svg')


@app.route('/static/img/<path:path>')
def serve_images(path):
    return send_from_directory('static/img', path)

app.run(debug=True)
