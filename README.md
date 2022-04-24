# Tareas-SOM
Tareas Bases Datos

----Qué contactos de proveedores tienen la posición de sales representative?

select * from suppliers s;

select s.contact_name
from suppliers s 
where contact_title ='Sales Representative';

-----Qué contactos de proveedores no son marketing managers?
select s.contact_name 
from suppliers s 
where contact_title !='Marketing Manager';
