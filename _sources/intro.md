# Ejercicio No.2 

Ejercicio para entregar

1. El siguiente informe debe ser presentado usando Jupyter Book. Por lo tanto, la entrega realizada corresponde a un link de una página de GitHub similar a la del presente curso. Debe crear una conexión con pgAdmin para mostrar las tablas creadas, agregar imágenes.

2. Crear una instancia de base de datos en Docker la cual utilizará para la solución de los siguientes ejercicios. Luego de finalizar con cada una de las consultas requeridas, deberá exportar la imagen de la base de datos a un archivo nombrado como, primernombre_primerapellido_imagendocker.tar, ejemplo: lihki_rubio_imagendocker.tar.

3. La imagen Docker y la base de datos que debe crear debe contar con la siguiente información de conexión. Nótese que debe usar la contraseña password.

Host: localhost

Port: 5342

Database Name: myname_db

User Name: myname_user

Password: password

4. Cada una de las siguientes consultas deben ser realizadas desde Python usando la API psycopg2. Por lo tanto, debe crear una conexión y un cursor previamente para realizar cada una de las siguientes consultas:

I) Crear la tabla nombrada: employees y explicar que tarea realiza la consulta realizada y mostrar en pantalla la tabla

CREATE TABLE employees
   ( employee_id INTEGER
   , first_name VARCHAR(20)
   , last_name VARCHAR(25)
   , email VARCHAR(25)
   , phone_number VARCHAR(20)
   , hire_date DATE
   , job_id VARCHAR(10)
   , salary NUMERIC(8,2)
   , commission_pct NUMERIC(2,2)
   , manager_id INTEGER
   , department_id INTEGER
   ) ;
CREATE UNIQUE INDEX emp_emp_id_pk
         ON employees (employee_id) ;
ALTER TABLE employees ADD
   PRIMARY KEY (employee_id);
SELECT * FROM employees LIMIT 10;
SELECT count(1) FROM employees;
II) Crear la tabla courses con las siguientes columnas:

course_id - integer y primary key

course_name - valores alfanuméricos o de cadena de hasta 60 caracteres

course_author - nombre del autor de hasta 40 caracteres

course_status - published, draft, inactive.

course_published_dt - valor de tipo fecha.

III) Insertar datos

Inserte los datos en courses utilizando los datos proporcionados. Asegúrese de que el id es generado por el sistema. No olvide refrescar la información de la base de datos.

_images/tableforexercise_python.png
Fig. 79 Filas a insertar en la tabla courses

IV) Borre todos los cursos que no estén en modo borrador ni publicados. Proporcione la sentencia de borrado como respuesta para este ejercicio en el Jupyter Book. Para validar, obtenga el recuento de todos los cursos publicados por autor y asegúrese de que la salida está ordenada en forma descendente por recuento.

VI) Crear la base de datos users

CREATE TABLE users(
    user_id SERIAL PRIMARY KEY,
    user_first_name VARCHAR(30),
    user_last_name VARCHAR(30),
    user_email_id VARCHAR(50),
    user_gender VARCHAR(1),
    user_unique_id VARCHAR(15),
    user_phone_no VARCHAR(20),
    user_dob DATE,
    created_ts TIMESTAMP
)
Inserte los siguientes valores

insert into users (
    user_first_name, user_last_name, user_email_id, user_gender, 
    user_unique_id, user_phone_no, user_dob, created_ts
) VALUES
    ('Giuseppe', 'Bode', 'gbode0@imgur.com', 'M', '88833-8759', 
     '+86 (764) 443-1967', '1973-05-31', '2018-04-15 12:13:38'),
    ('Lexy', 'Gisbey', 'lgisbey1@mail.ru', 'F', '262501-029', 
     '+86 (751) 160-3742', '2003-05-31', '2020-12-29 06:44:09'),
    ('Karel', 'Claringbold', 'kclaringbold2@yale.edu', 'F', '391-33-2823', 
     '+62 (445) 471-2682', '1985-11-28', '2018-11-19 00:04:08'),
    ('Marv', 'Tanswill', 'mtanswill3@dedecms.com', 'F', '1195413-80', 
     '+62 (497) 736-6802', '1998-05-24', '2018-11-19 16:29:43'),
    ('Gertie', 'Espinoza', 'gespinoza4@nationalgeographic.com', 'M', '471-24-6869', 
     '+249 (687) 506-2960', '1997-10-30', '2020-01-25 21:31:10'),
    ('Saleem', 'Danneil', 'sdanneil5@guardian.co.uk', 'F', '192374-933', 
     '+63 (810) 321-0331', '1992-03-08', '2020-11-07 19:01:14'),
    ('Rickert', 'O''Shiels', 'roshiels6@wikispaces.com', 'M', '749-27-47-52', 
     '+86 (184) 759-3933', '1972-11-01', '2018-03-20 10:53:24'),
    ('Cybil', 'Lissimore', 'clissimore7@pinterest.com', 'M', '461-75-4198', 
     '+54 (613) 939-6976', '1978-03-03', '2019-12-09 14:08:30'),
    ('Melita', 'Rimington', 'mrimington8@mozilla.org', 'F', '892-36-676-2', 
     '+48 (322) 829-8638', '1995-12-15', '2018-04-03 04:21:33'),
    ('Benetta', 'Nana', 'bnana9@google.com', 'M', '197-54-1646', 
     '+420 (934) 611-0020', '1971-12-07', '2018-10-17 21:02:51'),
    ('Gregorius', 'Gullane', 'ggullanea@prnewswire.com', 'F', '232-55-52-58', 
     '+62 (780) 859-1578', '1973-09-18', '2020-01-14 23:38:53'),
    ('Una', 'Glayzer', 'uglayzerb@pinterest.com', 'M', '898-84-336-6', 
     '+380 (840) 437-3981', '1983-05-26', '2019-09-17 03:24:21'),
    ('Jamie', 'Vosper', 'jvosperc@umich.edu', 'M', '247-95-68-44', 
     '+81 (205) 723-1942', '1972-03-18', '2020-07-23 16:39:33'),
    ('Calley', 'Tilson', 'ctilsond@issuu.com', 'F', '415-48-894-3', 
     '+229 (698) 777-4904', '1987-06-12', '2020-06-05 12:10:50'),
    ('Peadar', 'Gregorowicz', 'pgregorowicze@omniture.com', 'M', '403-39-5-869', 
     '+7 (267) 853-3262', '1996-09-21', '2018-05-29 23:51:31'),
    ('Jeanie', 'Webling', 'jweblingf@booking.com', 'F', '399-83-05-03', 
     '+351 (684) 413-0550', '1994-12-27', '2018-02-09 01:31:11'),
    ('Yankee', 'Jelf', 'yjelfg@wufoo.com', 'F', '607-99-0411', 
     '+1 (864) 112-7432', '1988-11-13', '2019-09-16 16:09:12'),
    ('Blair', 'Aumerle', 'baumerleh@toplist.cz', 'F', '430-01-578-5', 
     '+7 (393) 232-1860', '1979-11-09', '2018-10-28 19:25:35'),
    ('Pavlov', 'Steljes', 'psteljesi@macromedia.com', 'F', '571-09-6181', 
     '+598 (877) 881-3236', '1991-06-24', '2020-09-18 05:34:31'),
    ('Darn', 'Hadeke', 'dhadekej@last.fm', 'M', '478-32-02-87', 
     '+370 (347) 110-4270', '1984-09-04', '2018-02-10 12:56:00'),
    ('Wendell', 'Spanton', 'wspantonk@de.vu', 'F', null, 
     '+84 (301) 762-1316', '1973-07-24', '2018-01-30 01:20:11'),
    ('Carlo', 'Yearby', 'cyearbyl@comcast.net', 'F', null, 
     '+55 (288) 623-4067', '1974-11-11', '2018-06-24 03:18:40'),
    ('Sheila', 'Evitts', 'sevittsm@webmd.com', null, '830-40-5287',
     null, '1977-03-01', '2020-07-20 09:59:41'),
    ('Sianna', 'Lowdham', 'slowdhamn@stanford.edu', null, '778-0845', 
     null, '1985-12-23', '2018-06-29 02:42:49'),
    ('Phylys', 'Aslie', 'paslieo@qq.com', 'M', '368-44-4478', 
     '+86 (765) 152-8654', '1984-03-22', '2019-10-01 01:34:28')
VII) Obtenga el número de usuarios creados por año. Utilice la tabla de usuarios para este ejercicio.

La salida debe contener el año de 4 dígitos y el recuento.

Use funciones específicas de fecha para obtener el año usando created_ts.

Asegúrese de definir alias a las columnas como created_year y user_count respectivamente.

Los datos deben ordenarse de forma ascendente por created_year.

Cuando ejecutes la consulta usando el entorno Jupyter, puede que tenga decimales para los enteros. Por lo tanto, puede mostrar los resultados incluso con decimales.

_images/outputexercisevii_python.png
Fig. 80 Ejemplo de salida que debe obtener a partir de este ejercicio.

VIII) Obtenga los días de nacimiento de todos los usuarios nacidos en el mes May.

Utilice la tabla users para este ejercicio.

La salida debe contener user_id, user_dob, user_email_id y user_day_of_birth.

Utilice funciones específicas de fecha para obtener el mes utilizando user_dob.

user_day_of_birth debe ser un día completo con el primer carácter en mayúsculas, por ejemplo Tuesday.

Los datos deben ordenarse por día dentro del mes May.

_images/maybirths_exercise.png
Fig. 81 Ejemplo de salida para nacimientos en el mes de mayo.

IX) Obtenga los nombres e ids de correo electrónico de los usuarios añadidos en el año 2019.

Utilice la tabla users para este ejercicio.

La salida debe contener user_id, user_name, user_email_id, created_ts, created_year.

Utilice funciones específicas de fecha para obtener el año utilizando created_ts.

user_name es una columna derivada de concatenar user_first_name y user_last_name con un espacio en medio.

user_name debe tener valores en mayúsculas.

Los datos deben ordenarse en forma ascendente por user_name

_images/usernameorder_exercise.png
Fig. 82 Ejemplo de salida para nombres, ids, correo electrónico y fechas.

X) Obtenga el número de usuarios por género. Utilice la tabla de users para este ejercicio.

La salida debe contener el gender y user_count.

Para los hombres la salida debe mostrar Male y para las mujeres la salida debe mostrar Female.

Si no se especifica el sexo, se mostrará Not Specified

Los datos deben ordenarse en forma descendente por user_count.

_images/outputexercisex_python.png
Fig. 83 Ejemplo de salida para el ejercicio X.

XII) Obtenga los 4 últimos dígitos de los ids únicos.

Utilice la tabla users para este ejercicio.

El resultado debe contener user_id, user_unique_id y user_unique_id_last4.

Los identificadores únicos son null o not null.

Los identificadores únicos contienen números y guiones y son de diferente longitud.

Necesitamos obtener los últimos 4 dígitos descartando los guiones sólo cuando el número de dígitos es al menos 9.

Si el identificador único es nulo, debe mostrarse Not Specified.

Después de descartar los guiones, si el identificador único tiene menos de 9 dígitos, debe mostrar Invalid Unique Id.

Los datos deben ordenarse por user_id. Es posible que aparezca None o null para aquellos identificadores de usuario en los que no haya un identificador único para user_unique_id.

_images/exercisexii_python.png
Fig. 84 Ejemplo de output para Ejercicio XII.

XIII) Obtenga el recuento de usuarios en función del código de país.

Utilice la tabla users para este ejercicio.

La salida debe contener el código de país y el recuento.

No debe haber ningún + en el código de país. Sólo debe contener dígitos.

Los datos deben ordenarse como números por código de país.

Debemos descartar user_phone_no con valores null.

_images/usercountexercisexiii_python.png
Fig. 85 Ejemplo de output para ejercicio de recuento de usuarios en función del código de país.

5. Importe los datos del precio de Cardano USD (ADA-USD) en su instancia de base de datos Docker, teniendo en cuenta lo explicado durante esta sección. Luego dibuje un gráfico de candlestick para la criptomoneda. En el siguiente link encontrará el CSV de Cardano: Cardano USD (ADA-USD). Describa lo que puede observar en la serie de tiempo. Realice un análisis exploratorio de datos (EDA) para la serie de tiempo.

```{tableofcontents}
```