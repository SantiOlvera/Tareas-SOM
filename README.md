# Tareas-SOM
Tareas Bases Datos

1) Qué contactos de proveedores tienen la posición de sales representative?

select s.contact_name from suppliers s where contact_title ='Sales Representative';

2) Qué contactos de proveedores no son marketing managers?

select s.contact_name 
from suppliers s 
where contact_title !='Marketing Manager';

