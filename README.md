# Tareas-SOM
Tareas Bases Datos

1) Qué contactos de proveedores tienen la posición de sales representative?

select s.contact_name from suppliers s where contact_title ='Sales Representative';

2) Qué contactos de proveedores no son marketing managers?

select s.contact_name 
from suppliers s 
where contact_title !='Marketing Manager';

3) Cuales órdenes no vienen de clientes en Estados Unidos?

select o.order_id
from orders o join customers c using(customer_id)
where c.country !='USA';

4) Qué productos de los que transportamos son quesos?

select p.product_name 
from categories c join products p using(category_id)
join order_details od using(product_id)
join orders o using(order_id)
where shipped_date is not null and c.description ='Cheeses'
group by p.product_name ;

5) Qué ordenes van a Bélgica o Francia?

select o.order_id 
from orders o 
where (o.ship_country='Belgium' or o.ship_country='France') and shipped_date is null;

6) Qué órdenes van a LATAM?

select o.order_id 
from orders o 
where (o.ship_country ='Mexico' or o.ship_country='Argentina' or o.ship_country='Venezuela' or o.ship_country='Brazil') and shipped_date is  null;

7) Qué órdenes no van a LATAM?

select o.order_id 
from orders o 
where (o.ship_country !='Mexico' and o.ship_country!='Argentina' and o.ship_country!='Venezuela' and o.ship_country!='Brazil') and shipped_date is null;

8) Necesitamos los nombres completos de los empleados, nombres y apellidos unidos en un mismo registro

select concat(e.first_name,' ',e.last_name ) 
from employees e ;

9) Cuánta lana tenemos en inventario?

select sum(p.unit_price*p.units_in_stock)
from products p 
where p.units_in_stock >0;

10) Cuantos clientes tenemos de cada país?

select  c.country, count(c.customer_id) 
from customers c
group by c.country;
