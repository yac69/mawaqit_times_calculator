# Mawaqit Python Library
A python package around https://mawaqit.net's API. Only tested on python3.

## Installation

You can install the library from [PyPI](https://pypi.org/project/mawaqit_times_calculator/):

    pip install mawaqit_times_calculator



## How to use

from mawaqit_times_calculator import MawaqitTimesCalculator


#  parameters

mawaqit_login: a@a.com   # your mawaqit login

mawaqit_password: aaa    # your mawaqit passwor

 or 
 
mawaqit_api: "aaaaa-aaaa-aaaa"   # your mawaqit api_token 

lat = 45.7754498

long = 4.7785644

optionally, the moque id could be provided if known

mosque-id = "fd646008-a351-44bc-bde8-44380962f972" # if you know the mawaqit id of your mosque


mawaqit = MawaqitTimesCalculator(
    latitude=lat,
    longitude=long,
    mosque=''
    login=mawaqit_login,
    password=mawaqit_password,
    token=''
)

mawaqit.fetch_prayer_times()

provides the prayer time in the nearest mosque from your gps coordinates and all the usefull information on your mosque. the json looks like:

{'Fajr': '04:28', 'Sunrise': '06:08', 'Dhuhr': '13:42', 'Asr': '17:41', 'Sunset': '21:08', 'Maghrib': '21:08', 'Isha': '22:39', 'Imsak': '04:18', 'Midnight': '00:00', 'Jumua': '12:15', 'Shuruq': '06:08', 'Mosque': {'id': 3084, 'uuid': 'fd646008-a351-44bc-bde8-44380962f972', 'name': 'مسجد التوبة - Lyon', 'label': 'مسجد التوبة - Lyon', 'streamUrl': '', 'paymentWebsite': None, 'localisation': '5 rue Maurice Béjart 69009 Lyon France', 'countryCode': 'FR', 'phone': '0033478200336', 'email': 'acmduchere@gmail.com', 'site': 'https://www.facebook.com/MosqueeDuchere', 'association': 'ACMD', 'image': 'https://mawaqit.net/upload/mosque/5c/0e/a0/5c0ea06737036383745520.jpg', 'url': 'https://mawaqit.net/fr/attawba-lyon', 'latitude': 45.7882926, 'longitude': 4.7930922, 'hijriAdjustment': -1, 'aidPrayerTime': None, 'aidPrayerTime2': None, 'jumua': '12:15', 'jumua2': '13:00', 'jumuaAsDuhr': False, 'imsakNbMinBeforeFajr': 0, 'shuruq': '06:08', 'times': ['04:28', '13:42', '17:41', '21:08', '22:39'], 'womenSpace': True, 'janazaPrayer': True, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': True, 'otherInfo': "La mosquée ouvre une demie heure avant l'Adhane et ferme vingt minute après la Salat.\r\nLa mosquée reste ouverte entre le Maghreb et le Ichaa.", 'hijriDateForceTo30': False, 'updatedAt': 1621139217, 'announcements': [{'id': 29682, 'title': 'Info Prière de la DJoumouaa', 'content': 'Information \r\nSalat AL-Djoumouaa\r\nIL est porté à la connaissance des fidèles de la mosquée AT-Tawba qu’on organise deux prêches de la Djoumouaa, la Mosquée ouvre à partir de 11h30.\r\nLa première Djoumouaa commence à 12h15\r\nLa deuxième Djoumouaa commence à 13h00\r\nEn respectant la règle de distanciation, les places étant limitées, les portes seront fermées dès que le nombre de places maximum est atteint.\r\nMerci de votre Compréhension\r\nنسأل الله العليُّ القدير أن يرفع عنّا هذا البلاء', 'image': None, 'video': None, 'startDate': None, 'endDate': None, 'updated': '2021-04-15 04:47', 'isMobile': True, 'isDesktop': False}], 'events': []}}



mawaqit.all_mosques_neighberhood()

provides all the mosques in your neighborhood sorted from the nearest to the farthest

[{'uuid': '83028827-d50e-4893-ab93-52aeaa3ce328', 'id': 2145, 'name': 'El AMINE', 'slug': 'el-amine-lyon', 'latitude': 45.7682703, 'longitude': 4.7966933, 'associationName': 'Centre culturel musulman de vaise', 'phone': '0033669679779', 'paymentWebsite': None, 'email': 'nouariazzouz@gmail.com', 'site': None, 'womenSpace': None, 'janazaPrayer': None, 'aidPrayer': None, 'childrenCourses': None, 'adultCourses': None, 'ramadanMeal': None, 'handicapAccessibility': None, 'ablutions': None, 'parking': None, 'otherInfo': None, 'label': 'El AMINE - Lyon', 'localisation': '84 rue Sidoine apolinaire 69009 Lyon FRANCE', 'jumua': '13:00', 'jumua2': None, 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/bundles/app/prayer-times/img/default.jpg', 'proximity': 1616, 'times': ['04:23', '06:08', '13:37', '17:41', '21:07', '23:11'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': 'fd646008-a351-44bc-bde8-44380962f972', 'label': 'مسجد التوبة - Lyon', 'name': 'مسجد التوبة', 'id': 3084, 'slug': 'attawba-lyon', 'associationName': 'ACMD', 'phone': '0033478200336', 'site': 'https://www.facebook.com/MosqueeDuchere', 'paymentWebsite': None, 'email': 'acmduchere@gmail.com', 'localisation': '5 rue Maurice Béjart 69009 Lyon France', 'latitude': 45.7882926, 'longitude': 4.7930922, 'womenSpace': True, 'janazaPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': True, 'aidPrayer': True, 'otherInfo': "La mosquée ouvre une demie heure avant l'Adhane et ferme vingt minute après la Salat.\r\nLa mosquée reste ouverte entre le Maghreb et le Ichaa.", 'jumua': '12:15', 'jumua2': '13:00', 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5c/0e/a0/5c0ea06737036383745520.jpg', 'proximity': 1818, 'times': ['04:28', '06:08', '13:42', '17:41', '21:08', '22:39'], 'iqama': ['+15', '+7', '+7', '+7', '+7']}, {'uuid': 'dba1888c-9bdb-4dc8-81dd-75cd8dcdcada', 'id': 6101, 'name': 'مسجد الروضة', 'slug': 'rawda-lyon', 'latitude': 45.7780669, 'longitude': 4.8074444, 'associationName': 'ASSOCIATION ECCOL', 'phone': None, 'paymentWebsite': None, 'email': None, 'site': None, 'womenSpace': True, 'janazaPrayer': False, 'aidPrayer': False, 'childrenCourses': False, 'adultCourses': False, 'ramadanMeal': False, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': None, 'label': 'مسجد الروضة - Lyon', 'localisation': '12 RUE DE SAINT CYR 69009 Lyon France', 'jumua': None, 'jumua2': None, 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5e/69/b8/5e69b848bf16b800750581.JPG', 'proximity': 2258, 'times': ['04:28', '06:08', '13:42', '17:41', '21:08', '22:39'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': 'c929421d-5931-4dfd-9a8a-94195a3770b1', 'id': 6302, 'name': 'Mosquée Al Houda مسجد الهدى', 'slug': 'el-houda-lyon5', 'latitude': 45.7563556, 'longitude': 4.8122181, 'associationName': 'Al Houda', 'phone': '0033768648774', 'paymentWebsite': None, 'email': 'alhouda69005@gmail.com', 'site': 'http://alhouda69005@gmail.com', 'womenSpace': False, 'janazaPrayer': False, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': False, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': 'Iftar Uniquement pour les étudiants "cause d\'espace"', 'label': 'Mosquée Al Houda مسجد الهدى - Lyon', 'localisation': '21 rue des fossés de Trion 69005 Lyon France', 'jumua': '13:00', 'jumua2': None, 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5e/39/93/5e39936d2e48b919416398.jpg', 'proximity': 3364, 'times': ['04:33', '06:08', '13:42', '17:43', '21:10', '22:30'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': '102d766c-af02-472b-a07d-eab6554988ba', 'id': 3838, 'name': 'مسجد قباء Mosquée Koba', 'slug': 'koba-lyon', 'latitude': 45.7712985, 'longitude': 4.8327583, 'associationName': 'ASSOCIATION ISLAMIQUE CROIX ROUSSE MOSQUEE KOBA', 'phone': None, 'paymentWebsite': None, 'email': None, 'site': None, 'womenSpace': False, 'janazaPrayer': False, 'aidPrayer': False, 'childrenCourses': False, 'adultCourses': False, 'ramadanMeal': False, 'handicapAccessibility': False, 'ablutions': False, 'parking': False, 'otherInfo': "Ouverture 15min avant al'adhan\r\nFermeture 10min après fin de prière", 'label': 'مسجد قباء Mosquée Koba - Lyon', 'localisation': '10 RUE IMBERT COLOMES 69001 Lyon France', 'jumua': '13:00', 'jumua2': '13:45', 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5c/9f/4f/5c9f4ff53c36c792311550.jpg', 'proximity': 4228, 'times': ['04:28', '06:08', '13:42', '17:41', '21:08', '22:39'], 'iqama': ['05:05', '+10', '+10', '+10', '+10']}, {'uuid': '39f66461-6d4c-46f4-8c46-aef7a9ac4bbe', 'id': 8075, 'name': 'مسجد براش', 'slug': 'perrache-lyon', 'latitude': 45.7426359, 'longitude': 4.8239134, 'associationName': 'Association culturelle de la mosquée  Perrache  confluence', 'phone': None, 'paymentWebsite': 'http://paypal.me/mosqueeperrache', 'email': 'mosquee.perrache@gmail.com', 'site': None, 'womenSpace': False, 'janazaPrayer': False, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': False, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': None, 'label': 'مسجد براش - Lyon', 'localisation': '28 cours Bayard 69002 Lyon France', 'jumua': '13:00', 'jumua2': None, 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5f/e1/04/5fe104af2af3c479204662.jpg', 'proximity': 5068, 'times': ['04:28', '06:08', '13:42', '17:41', '21:08', '22:39'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': '19e23a4f-db1b-4b64-991c-aa3b60ed2fba', 'id': 1849, 'name': 'مسجد أبو بكر الصديق', 'slug': 'aboubakr69003', 'latitude': 45.7570348, 'longitude': 4.8438032, 'associationName': 'Association cultuelle Abou Bakr Essedik', 'phone': '0033478626898', 'paymentWebsite': None, 'email': 'acabe69@orange.fr', 'site': None, 'womenSpace': True, 'janazaPrayer': True, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': 'Votre Mosquée est ouverte 30 minutes avant chaque prière et fermera 30 minutes après.', 'label': 'مسجد أبو بكر الصديق - Lyon', 'localisation': '14 rue villeroy 69003 Lyon France', 'jumua': '12:00', 'jumua2': '13:00', 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/bundles/app/prayer-times/img/default.jpg', 'proximity': 5459, 'times': ['04:26', '06:08', '13:43', '17:42', '21:10', '22:30'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': 'a2531b31-a565-41c0-ae7c-b0e1fbab1a55', 'id': 7502, 'name': 'مسجد مصعب بن عمير - Mosaab ibn Omayer', 'slug': 'mosaab-lyon', 'latitude': 45.7528459, 'longitude': 4.8449581, 'associationName': 'Association Culturelle des Musulmans de France', 'phone': None, 'paymentWebsite': None, 'email': None, 'site': None, 'womenSpace': False, 'janazaPrayer': False, 'aidPrayer': True, 'childrenCourses': False, 'adultCourses': False, 'ramadanMeal': False, 'handicapAccessibility': False, 'ablutions': True, 'parking': False, 'otherInfo': None, 'label': 'مسجد مصعب بن عمير - Mosaab ibn Omayer - Lyon', 'localisation': '15 rue Sebastien Gryphe 69007 Lyon France', 'jumua': '12:30', 'jumua2': None, 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5f/1b/97/5f1b9722886da142482218.jpeg', 'proximity': 5730, 'times': ['04:23', '06:08', '13:37', '17:41', '21:07', '22:52'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}, {'uuid': '775f3cf6-4a2a-4136-89a9-f2f38113acba', 'id': 4215, 'name': 'Mosquee Al Sakina', 'slug': 'assakina-caluire', 'latitude': 45.7887127, 'longitude': 4.8539994, 'associationName': 'LES AMIS DE ST CLAIR', 'phone': None, 'paymentWebsite': None, 'email': 'mosqueesakina@gmail.com', 'site': None, 'womenSpace': True, 'janazaPrayer': True, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': None, 'label': 'Mosquee Al Sakina - Caluire', 'localisation': '86 GRANDE RUE DE ST CLAIR 69300 Caluire France', 'jumua': '12:30', 'jumua2': '13:15', 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5c/cd/a4/5ccda40aa2e53207224545.jpg', 'proximity': 6032, 'times': ['04:27', '06:08', '13:37', '17:41', '21:07', '22:39'], 'iqama': ['+', '+', '+', '+', '+']}, {'uuid': 'e9f4fcd3-27c3-4b12-8727-571e56699c4d', 'id': 7694, 'name': 'مسجد الوسيلة - El - Wassila', 'slug': 'el-wassila-lyon', 'latitude': 45.7506189, 'longitude': 4.849828, 'associationName': 'El - Wassila', 'phone': None, 'paymentWebsite': None, 'email': 'fenni@me.com', 'site': 'http://elwassila.com', 'womenSpace': True, 'janazaPrayer': False, 'aidPrayer': True, 'childrenCourses': True, 'adultCourses': True, 'ramadanMeal': True, 'handicapAccessibility': True, 'ablutions': True, 'parking': False, 'otherInfo': None, 'label': 'مسجد الوسيلة - El - Wassila - Lyon', 'localisation': '52 rue Rachais 69007 Lyon France', 'jumua': '12:30', 'jumua2': '13:20', 'jumuaAsDuhr': False, 'image': 'https://mawaqit.net/upload/mosque/5f/5c/38/5f5c386633a54583973459.jpeg', 'proximity': 6179, 'times': ['04:29', '06:08', '13:47', '17:41', '21:12', '22:41'], 'iqama': ['+10', '+10', '+10', '+5', '+10']}]



