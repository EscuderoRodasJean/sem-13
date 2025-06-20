# sem-13****

-- Crear procedimiento que liste/ muestre los porductos (ID-Nombre-PrecioUNi- Stock)

/*mostrar producto*/

select * From  Products 

select ProductID, ProductName, UnitPrice,UnitsInStock from Products

create procedure SP_ListayMuestra

create procedure SP_ListarPro
AS
BEGIN
select ProductID, ProductName, CategoryID, UnitPrice,UnitsInStock 
from Products
END

execute SP_ListarPro


--Crear un procedimiento Almacenado (SP) donde se busque al empleado por codigo


alter procedure SP_BusquedaXCod(@country nvarchar(15))
AS
BEGIN
select * 
from Employees 
where Country like @country
END

 

create procedure SP_BusquedaXApellido(@LastName nvarchar(15))
AS
BEGIN
select * 
from Employees 
where LastName like @LastName
END

exec SP_BusquedaXApellido 'D%'


--Crear un procedimiento Almacenado (SP) donde se busque a lo(s) cliente(s) por ciudad

select * from Customers where city like 'london'

alter procedure SP_BusquedaXcuidad(@city nvarchar(15),
@CODPOSTAL nvarchar(10))
AS
BEGIN
select * 
from Customers 
where city like @city and PostalCode=@CODPOSTAL
END

EXEC SP_BusquedaXcuidad 'london','EC2 5NT'





/*SP_

Generar un Procedimiento almacenado (SP_...) utilizando el "Northwind"
--1-Q consulte una tabla cualquiera mostrando todos los campos (*)
-----------------------------------------------------------------*/

Create procedure SP_MostrarEmp
AS
BEGIN
select *from Employees 
END

exec SP_MostrarEmp

/*2-Q consulte una tabla cualquiera mostrando CAmpos agrupados (Group by ...)
---------------------------------------------------------------------------*/

create procedure SP_mostrarxgrupo
AS
BEGIN
select city,count(*) from Employees 
group by city
END

exec SP_mostrarxgrupo
/*3- Que consulte enviando 1 parametro (WHERE) (Lo necesario) 
-----------------------------------------------------------*/


alter procedure SP_mostrar(
--parametro consulte tipo de dato)
AS
BEGIN
select * from Employees 
Where .... --con parametro
END

exec SP_mostrar



-------------------------------------------------------------
-------------------------------------------------------------
/*PLUS PARA REVISAR*/

/**********************/
--Crear un procedimiento almacenado que muestre todos los campos de los EMPLEADOS
/**********************/
--conocer al shipper

create procedure SP_ShippersInsertaNuevo
(@Companyname nvarchar(40),@Phone nvarchar(24))
As
BEGIN
insert into Shippers (CompanyName, Phone)
values (@CompanyName,@Phone)
select * from Shippers
END

exec SP_ShippersInsertaNuevo 'UTP','88888'
exec SP_ShippersInsertaNuevo 'UTP','88889'

insert into Shippers (CompanyName, Phone)
values ('Tolva Couriers','954542452')



select * from Shippers


/********************************************/

create procedure SP_ShippersInsertaNuevo
(
@NombreEmpresa nvarchar(40),
@Fono nvarchar(24)
)
As
BEGIN
insert into Shippers (CompanyName, Phone)
values (@NombreEmpresa,@Fono)
END
go

exec SP_ShippersInsertaNuevo 'TolvA cO', '9545424512'
execute SP_ShippersInsertaNuevo 'TolvA cO', '9545424512'

/**********************/
--DIAPO 6
--Crear un procedimiento almacenado que muestre todos los campos de los EMPLEADOS por Ciudad ()
/**********************/
create procedure SP_ShippersEliminarID(@ShipperID int)
As
BEGIN
delete from Shippers
where ShipperID= @ShipperID
select * from Shippers
END

create procedure SP_ShippersEliminarID(@ShipperID int)
As
BEGIN
delete from Shippers
where ShipperID= @ShipperID
select * from Shippers
END

execute SP_ShippersEliminarID 6
execute SP_ShippersEliminarID 7
execute SP_ShippersEliminarID 8

select * from Employees

select * from Shippers

delete from Shippers where ShipperID between 5 and 6

----------------------------------------------------------------
--Crear un SP para actualizar precio aplicando codigo de un producto especifico:
                              ------           -------   

select * from Products

execute SP_AjustePrecio 20.5, 1;

create procedure SP_AjustePrecio (
@NuevoPrecio money,
@CodProd int) 
AS
BEGIN

UPDATE Products
SET UnitPrice=@NuevoPrecio 
WHERE ProductID=@CodProd

END





/************ FUNCIONES (DEFICINAS POR EL USUARIO) **********/

--SINTAXIS:

CREATE FUNCTION <NombreDeLaFuncion> (<@parametro 1> AS TipoDato, <@parametro2> AS TipoDato)
RETURNS TipoDato
AS
BEGIN
	DECLARE <@parametro Salida> AS TipoDato--Esta linea es para declarar el 
	SET <@parametro Salida> = <@parametrosEntrada>
	    <operacion / sentencia / consulta> 
	RETURN <@parametro Salida>
END


/*Crear una funcion que saque el AREA de un TRIANGULO*/
/*****************************************************/

------------------------Sin parametro de salida-----------------------------

create function S_AREA_TRI (@base as decimal(10,2), @altura as decimal(10,2))
RETURNS decimal(10,2)
AS
Begin 
	RETURN (@base*@altura)/2
END

--Mostrar la funci n:
select dbo.S_AREA_TRI(4,8) 

------------------------Con parametro de salida--------------------------------

create function C_AREA_TRI (@base as decimal, @altura as decimal)
returns decimal
AS
Begin 
declare @R as decimal -----Declarar la variable de salida
Set @R= (@base*@altura)/2   ----- SET colocar valores a esa variable de salida
RETURN @R
END

create function C_AREA_CIRC (@base as decimal, @altura as decimal)
returns decimal
AS
Begin 
declare @R as decimal -----Declarar la variable de salida
Set @R= (@base*@altura)/2   ----- SET colocar valores a esa variable de salida
RETURN @R
END

--Mostrar la funci n:
select dbo.C_AREA_TRI(4,8)

---------------------------------------------------------------------
--Imprimir en consola + Transfomacion de tipodedatos
PRINT 'El area del Triangulo es:' + CAST(dbo.C_AREA_TRI(4,8) AS NVARCHAR)  






-------------------------------------------------------------------
---------------------------DIAPOSITIVA 05--------------------------
--Se requiere obtener el total de los PRODUCTOS VENDIDOS al ingresar el ID

select * from OrderDetails

select OrderID, sum(UnitPrice*Quantity) from OrderDetails
--WHERE OrderID=10251
group by OrderID


alter function TotalXID(@ID as int)
returns money
AS
Begin 
	declare @TOTAL as money

	SELECT @TOTAL=sum(UnitPrice*Quantity) from OrderDetails
	WHERE OrderID=@ID

	RETURN @TOTAL
END


select dbo.TotalXID(10252)


-------------------------------------------------------------------
---------------------------DIAPOSITIVA 07--------------------------
--Se requiere mostrar a todos los CLIENTES al ingresar su PAIS

select * from Customers


select CustomerID,CompanyName,Country from Customers
where Country like 'France'


create function ClienteXPais(@Pais as nvarchar(15))
returns TABLE -------cambio el tipo de retorno
AS
	RETURN (
		select CustomerID,CompanyName,Country from Customers
		where Country like @Pais
		)


select * from dbo.ClienteXPais('UK')






/****************** TAREA S13 ***************************/

--1. Elegir una tabla al azar de la web, construirla con sus respectivos campos y restricciones, crear un SP_ para registrar, 
--   otro para actualizar y otro para eliminar, cada SENTENCIA con su(s) respectivo(s) parametro(s) (Todos estos pasos deben ser explicados)
--2. Crear una funcion con un parametro de entrada, que retorne una tabla al consultar (Apoyarse en la pregunta 1).
--3. Crear una funcion que calcule el PROMEDIO de 2 n meros (2 parametros de entrada)
--4. Crear una funcion que calcule la SUMA de 3 numeros (3 parametros de entrada)
--5. Crear una funcion que calcule el AREA de un CUADRADO. 
