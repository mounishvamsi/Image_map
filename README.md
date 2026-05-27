# Ex03 Places Around Me
# Date:27.05.2026
# AIM
To develop a website to display details about the places around my house.

# DESIGN STEPS
## STEP 1
Create a Django admin interface.

## STEP 2
Download your city map from Google.

## STEP 3
Using <map> tag name the map.

## STEP 4
Create clickable regions in the image using <area> tag.

## STEP 5
Write HTML programs for all the regions identified.

## STEP 6
Execute the programs and publish them.

# CODE
view.py
```
from django.shortcuts import render

def chennai(request):
    return render(request, 'chennai.html')

def entrance(request):
    return render(request, 'entrance.html')

def map_view(request):      # use a different name because map() is a Python function
    return render(request, 'map.html')

def sec(request):
    return render(request, 'sec.html')

def sse(request):
    return render(request, 'sse.html')
```
urls.py
```from django.urls import path
from imageApp import views
from django.http import HttpResponseRedirect

urlpatterns = [
    path('', views.map_view, name='default_map'),  # Set 'map_view' as the default view for root
    path('chennai/', views.chennai, name='chennai'),
    path('entrance/', views.entrance, name='entrance'),
    path('map/', views.map_view, name='map'),
    path('sec/', views.sec, name='sec'),
    path('sse/', views.sse, name='sse'),
]
```
html code
```
1.map.html
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MAP</title>

    <style>
        h1 {
            text-align: center;
            color: rgb(39, 75, 231);
            margin-top: 20px;
        }

        img {
            display: block;
            margin-left: auto;
            margin-right: auto;
            /* width: 600px;
            height: 300px; */
            border-radius: 10px;
            margin-top: 15px;
        }

        p {
            text-align: justify;
            line-height: 25px;
            padding: 25px;
            font-size: 17px;
        }

    </style>
</head>

<body>


    <img src="{% static 'chennaiMap.png' %}" alt="SEC" usemap="#image-map">

<map name="image-map">
    <area target="_self" alt="chennai" title="chennai" href="{% url 'chennai' %}" coords="1123,355,1350,538" shape="rect"></area>
</map>

</body>

</html>

2.chennai.html
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SEC</title>

    <style>
        h1 {
            text-align: center;
            color: rgb(39, 75, 231);
            margin-top: 20px;
        }

        img {
            display: block;
            margin-left: auto;
            margin-right: auto;
            width: 600px;
            height: 300px;
            border-radius: 10px;
            margin-top: 15px;
        }

        p {
            text-align: justify;
            line-height: 25px;
            padding: 25px;
            font-size: 17px;
        }

        body {
            background-color: rgb(162, 225, 248);
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
</head>

<body>

    <h1>Chennai</h1>

    <img src="{% static 'CHENNAI.jpg' %}" alt="Chennai">

    <p>
        Chennai, the capital city of Tamil Nadu, stands as one of India’s most vibrant metropolitan regions, known for its rich cultural heritage, thriving economy, and coastal charm. As a city that beautifully blends tradition with modernity, Chennai attracts people from all over the country for education, employment, health care, and tourism. One of its most iconic features is Marina Beach, one of the longest urban beaches in the world, drawing millions of visitors each year. The city is also deeply rooted in classical arts—Bharatanatyam, Carnatic music, and traditional crafts flourish in its cultural centers and auditoriums, especially during the famous December music season. Chennai’s economy is robust, powered by IT hubs, automobile industries, healthcare institutions, and educational establishments that have positioned it as a major South Indian powerhouse. Architecturally, the city offers an impressive mix of ancient temples like Kapaleeshwarar Temple, colonial-era structures such as Fort St. George, and modern skyscrapers. Chennai is also renowned for its medical tourism, with world-class hospitals and research facilities attracting patients internationally. Its warm hospitality, safe environment, and disciplined urban culture make it a comfortable place to live. The city’s cuisine, marked by dosas, idlis, filter coffee, and seafood specialties, reflects the authentic flavors of Tamil tradition. Chennai’s transport network—metro lines, suburban trains, buses, and an international airport—ensures excellent connectivity. Despite rapid modernization, the city retains its old-world charm and cultural pride. With a harmonious blend of urban development and cultural preservation, Chennai continues to evolve into a global city while staying deeply connected to its roots.
    </p>
<a href="{% url 'entrance' %}">NEXT</a>
</body>

</html>

3.entrance.html
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Entrance</title>

    <style>
        h1 {
            text-align: center;
            color: rgb(39, 75, 231);
            margin-top: 20px;
        }

        img {
            display: block;
            margin-left: auto;
            margin-right: auto;
            width: 600px;
            height: 300px;
            border-radius: 10px;
            margin-top: 15px;
        }

        p {
            text-align: justify;
            line-height: 25px;
            padding: 25px;
            font-size: 17px;
        }

        body {
            background-color: rgb(162, 225, 248);
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
</head>

<body>

    <h1>Entrance</h1>

    <img src="{% static 'SAVEETHAENTRANCE.jpeg' %}" alt="Chennai">

    <p>
        Saveetha Medical College, located in Chennai, is one of India’s most distinguished institutions for medical education, research, and healthcare training. Known for its advanced infrastructure and student-friendly campus environment, the college has gained a reputation for excellence across academic and clinical domains. Its modern laboratories, digital classrooms, simulation centers, and state-of-the-art hospital facilities allow students to gain extensive hands-on training from the earliest stages of their education. The attached Saveetha Medical College Hospital, with its large patient inflow, provides students with real-time exposure to diverse medical cases, enabling them to develop practical skills and clinical confidence. The institution is also recognized for its strong focus on research, encouraging students and faculty to publish papers, participate in conferences, and engage in innovative medical studies. Saveetha places equal emphasis on holistic development, offering opportunities for sports, cultural events, and community outreach programs that help shape socially responsible medical professionals. The college fosters an environment of mentorship, with approachable faculty members who guide students academically and emotionally, ensuring a supportive learning atmosphere. Saveetha Medical College is also known for its disciplined, well-organized curriculum, incorporating modern teaching methodologies, technology-driven learning platforms, and problem-based learning approaches. The campus, surrounded by greenery and peaceful landscapes, offers a serene environment that enhances focus and well-being. With a commitment to producing compassionate, skilled, and globally competent doctors, Saveetha Medical College continues to be a preferred destination for aspiring medical professionals from across the country.
    </p>
<a href="{% url 'sse' %}">NEXT</a>
</body>

</html>

4.sse.html
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SSE</title>

    <style>
        h1 {
            text-align: center;
            color: rgb(39, 75, 231);
            margin-top: 20px;
        }

        img {
            display: block;
            margin-left: auto;
            margin-right: auto;
            width: 600px;
            height: 300px;
            border-radius: 10px;
            margin-top: 15px;
        }

        p {
            text-align: justify;
            line-height: 25px;
            padding: 25px;
            font-size: 17px;
        }

        body {
            background-color: rgb(162, 225, 248);
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
</head>

<body>

    <h1>SSE</h1>

    <img src="{% static 'sse.jpg' %}" alt="Chennai">

    <p>
        Saveetha University, also known as Saveetha Institute of Medical and Technical Sciences (SIMATS), is a prominent deemed university in Chennai that offers a wide range of educational programs across medicine, engineering, dental sciences, law, physiotherapy, nursing, and diverse allied health streams. The university is recognized for its interdisciplinary approach, encouraging students to explore a variety of academic fields and engage in collaborative learning. Saveetha University has built a reputation for innovation-driven education, supported by modern infrastructure, smart classrooms, skill development labs, and an ecosystem that promotes research and entrepreneurship. Its dental college is globally acclaimed for achieving world rankings, placing the university on the international academic map. The institution promotes a student-centric environment, offering mentorship, academic guidance, and personality development programs that prepare students for leadership roles in their respective professions. Along with academics, the campus emphasizes physical fitness, arts, and community service, ensuring holistic development. The university hosts several national and international conferences, workshops, and cultural events, giving students the opportunity to gain exposure beyond textbooks. With a strong commitment to research, Saveetha University encourages publication, innovation, and clinical studies supported by well-equipped labs and high-end technology. The campus environment is vibrant yet disciplined, offering safety, greenery, and an atmosphere conducive to focused learning. The university’s emphasis on ethics, integrity, and professional excellence makes its graduates highly respected in industries and institutions worldwide. Saveetha University’s continuous growth, academic achievements, and global collaborations showcase its mission to shape future-ready professionals equipped with knowledge, creativity, and compassion.
    </p>
<a href="{% url 'sec' %}">NEXT</a>
</body>

</html>

5.sec.html
{% load static %}
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SEC</title>

    <style>
        h1 {
            text-align: center;
            color: rgb(39, 75, 231);
            margin-top: 20px;
        }

        img {
            display: block;
            margin-left: auto;
            margin-right: auto;
            width: 600px;
            height: 300px;
            border-radius: 10px;
            margin-top: 15px;
        }

        p {
            text-align: justify;
            line-height: 25px;
            padding: 25px;
            font-size: 17px;
        }

        body {
            background-color: rgb(162, 225, 248);
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
</head>

<body>

    <h1>Saveetha Engineering College</h1>

    <img src="{% static 'SEC.jpeg' %}" alt="SEC">

    <p>
        Saveetha Engineering College, located on the outskirts of Chennai, is a premier institution dedicated to
        high-quality engineering education and technological advancement. Affiliated with Anna University, the college
        offers undergraduate and postgraduate programs across major engineering departments, including Computer Science,
        Electronics, Mechanical, Civil, Electrical, and Information Technology. Known for its modern academic framework
        and industry-oriented curriculum, Saveetha Engineering College equips students with both theoretical knowledge
        and practical skills.

        The well-maintained campus features advanced laboratories, innovation centers, libraries, workshops, and
        collaborative learning spaces that support academic excellence. The college has a strong placement record, with
        partnerships and tie-ups with leading MNCs, IT firms, manufacturing industries, and research organizations that
        offer internships, training, and job opportunities.

        Saveetha Engineering College also promotes extracurricular activities, technical clubs, hackathons, cultural
        festivals, and sports events that help students develop creativity, leadership qualities, and teamwork. Faculty
        members are experienced, approachable, and dedicated to guiding students in academics, research, and career
        planning.

        Its green and spacious campus provides a peaceful environment ideal for focused learning and personal growth. By
        combining strong academics with practical exposure and a supportive learning atmosphere, Saveetha Engineering
        College continues to shape engineers who are industry-ready, innovative, and prepared to contribute meaningfully
        to society.
    </p>

</body>

</html>
```



# OUTPUT
<img width="1848" height="874" alt="image" src="https://github.com/user-attachments/assets/ccd993d8-8af5-441c-856c-539bf0d91025" />

<img width="1851" height="869" alt="image" src="https://github.com/user-attachments/assets/fbb0b067-fd20-4ea4-a460-b1323f98500e" />

<img width="1848" height="878" alt="image" src="https://github.com/user-attachments/assets/62ab3359-a860-470a-a475-0aa66d309bc5" />

<img width="1849" height="866" alt="image" src="https://github.com/user-attachments/assets/c4c7a35e-80ba-4600-8f6b-5d8d11e4b579" />

<img width="1847" height="872" alt="image" src="https://github.com/user-attachments/assets/9b697790-d65f-4b4f-af30-81294cbc3bbc" />
























# RESULT
The program for implementing image maps using HTML is executed successfully.
