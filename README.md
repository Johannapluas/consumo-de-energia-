# Consumo-de-energia-

Para administrar la nueva matriz energética del Ecuador, Ud. tiene un diccionario con la información de las
plantas de energía y a las ciudades que atienden. Cada ciudad tiene: una tupla con los consumos mensuales
(12) del año en megavatios-hora (MWh) y la tarifa de consumo en dólares por megavatio-hora (MWh) que le
cobra la planta eléctrica. Una ciudad puede estar servida por más de una planta eléctrica. No todas las
ciudades son servidas por todas las plantas eléctricas.

```python
consumo_energia = {
 'Coca Codo Sinclair': {
 'Quito': { 'consumos':(400, 432, 400, 432, 420, 432, 460, 432, 400, 432, 300 , 213),'tarifa': 65},
 'Guayaquil': { 'consumos': (120, 55, 32, 120, 75, 32, 150, 55, 32, 120, 97, 32),'tarifa': 84},
 },
 'Sopladora': {
 'Guayaquil':{ 'consumos': (310, 220, 321, 310, 220, 321, 310, 220, 321, 310, 220, 321),'tarifa':55},
 'Quito': { 'consumos': (400, 432, 587, 400, 432, 587, 400, 432, 587, 400, 432, 587),'tarifa': 79},
 'Loja': { 'consumos': (50, 32, 32, 50, 32, 32, 50, 32, 32, 50, 32, 32),'tarifa': 32},
 },
}
```
Además, dispone del siguiente diccionario con información de ciudad por región:
```python
informacion = {
 'costa': ('Guayaquil', 'Manta'),
 'sierra': ('Quito', 'Ambato', 'Loja'),
 'oriente': ('Tena', 'Nueva Loja')
}
```
1. Solicite al usuario el nombre de una planta y de una ciudad y presente el total de megavatios de consumos para dicha ciudad en dicha planta.
2. Solicite al usuario el nombre de una ciudad y presente un nuevo diccionario cuyas claves son los nombres de las plantas generadoras y el total megavatios que cada planta le ha dado a ciudad. Si la planta no entrega energía a la ciudad entonces esa planta no debería aparecer en el nuevo diccionario.
3.Solicite el nombre de una región al usuario y presente cuento dinero ha recaudado la región Sierra. Nota: Todos los ingresos deben ser validados y repetir en caso de existir errores
