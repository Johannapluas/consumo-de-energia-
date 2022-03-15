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

RESPUESTA:😎
```python
consumo_energia = {
    'Coca Codo Sinclair':{
        'Quito': {'consumos': (400, 432, 400, 420, 432, 460, 432, 400, 432, 300, 213), 'tarifa': 65},
        'Guayaquil': {'consumos': (120, 55, 32, 120, 75, 32, 150, 55, 32, 120, 97, 32),'tarifa': 84},
    },
    'Sopladora': {
        'Guayaquil':{ 'consumos': (310, 220, 321, 310, 220, 321, 310, 220, 321, 310, 220, 321),'tarifa':55},
        'Quito': { 'consumos': (400, 432, 587, 400, 432, 587, 400, 432, 587, 400, 432, 587),'tarifa': 79},
        'Loja': { 'consumos': (50, 32, 32, 50, 32, 32, 50, 32, 32, 50, 32, 32),'tarifa': 32},
 },
}
tot_coca_codo_g = (120 + 55 + 32 + 120 + 75 + 32 + 150 + 55 + 32 + 120 + 97 + 32)
tot_coca_codo_q = (400 + 432 + 400 + 420 + 432 + 460 + 432 + 400 + 432 + 300 + 213)
tot_sopladora_g = (310 + 220 + 321 + 310 + 220 + 321 + 310 + 220 + 321 + 310 + 220 + 321)
tot_sopladora_q = (400 + 432 + 587 + 400 + 432 + 587 + 400 + 432 + 587 + 400 + 432 + 587)
tot_sopladora_l = (50 + 32 + 32 + 50 + 32 + 32 + 50 + 32 + 32 + 50 + 32 + 32)

informacion = {
 'costa': ('Guayaquil', 'Manta'),
 'sierra': ('Quito', 'Ambato', 'Loja'),
 'oriente': ('Tena', 'Nueva Loja')
}

costa = tot_coca_codo_g + tot_sopladora_g
sierra = tot_sopladora_q + tot_coca_codo_q + tot_sopladora_l
oriente = ('No hay planta en oriente')

print('''
          PLANTAS ENERGETICAS
    ''')
print('<1>. Total de MWH en Planta y Ciudad ')
print('<2>. Total de Energia por Ciudad ')
print('<3>. Dinero Recaudado por Region ')
print('<4>. Escriba (salir) para Salir del programa')
opcion = input('Elija una opcion: ')

if opcion == 'salir':
    exit

#1. Solicite al usuario el nombre de una planta y de una ciudad y presente el total de
#megavatios de consumos para dicha ciudad en dicha planta.
elif opcion == '1':
    
    print('''
        TOTAL DE MEGAVATIOS  PLANTAS
    Coca Codo Sinclair,Sopladora
              CIUDADES
    Guayaquil,Quito,Loja
  
    ''')

    n_planta = input('Ingrese el nombre de la planta: ')

    if n_planta == 'Coca Codo Sinclair':
        n_ciudad = input('Ingrese el nombre de la ciudad: ')

        if n_ciudad == 'Quito':
            print('Total de MWH de consumo en Coca Codo Sinclair, Quito: ', tot_coca_codo_q, 'MWH')
            print('Con tarifa de: ', consumo_energia['Coca Codo Sinclair']['Quito']['tarifa'])
        elif n_ciudad == 'Guayaquil':
            print('Total de MWH de consumo en Coca Codo Sinclair, Guayaquil: ', tot_coca_codo_g, 'MWH')
            print('Con tarifa de: ', consumo_energia['Coca Codo Sinclair']['Guayaquil']['tarifa'])
        elif n_ciudad =='Loja':
            print("No hay una planta de Coca Codo Sinclair en Loja")
    print()

    if n_planta == 'Sopladora':
        n_ciudad = input('Ingrese el nombre de la ciudad: ')

        if n_ciudad == 'Quito':
            print('Total de MWH de consumo en Sopladora, Quito: ', tot_sopladora_q, 'MWH')
            print('Con tarifa de: ', consumo_energia['Sopladora']['Quito']['tarifa'])
        elif n_ciudad == 'Guayaquil':
            print('Total de Megavatios de consumo en Sopladora, Guayaquil: ', tot_sopladora_g, 'MWH')
            print('Con tarifa de: ', consumo_energia['Sopladora']['Guayaquil']['tarifa'])
        elif n_ciudad == 'Loja':
            print('Total de Megavatios de consumo en Sopladora, Loja: ', tot_sopladora_l)
            print('Con tarifa de: ', consumo_energia['Sopladora']['Loja']['tarifa'])
    else:
        print("Digite correctamente la primera en mayuscula")

    exit
    
#2. Solicite al usuario el nombre de una ciudad y presente un nuevo diccionario cuyas claves
#son los nombres de las plantas generadoras y el valor es el total megavatios que cada
#planta le ha dado a ciudad. Si la planta no entrega energía a la ciudad entonces esa planta
#no debería aparecer en el nuevo diccionario  
elif opcion == '2':
    print('''
    TOTAL DE ENERGIA DADA A CADA  CIUDAD POR CADA PLANTA CIUDADES
    Guayaquil
    Quito
    Loja
    Ambato
    Tena
    Nueva loja
    '''),

    n_ciudad2 = input('Ingrese el nombre de la ciudad: ')

    if n_ciudad2 == 'Guayaquil':
        print('Total de MWH, Coca Codo Sinclair: ', tot_coca_codo_g, 'MWH')
        print('Total de MWH, Sopladora:', tot_sopladora_g, 'Megavatios')
    elif n_ciudad2 == 'Quito':
        print('Total de  MWH, Coca Codo Sinclair: ', tot_coca_codo_q, 'MWH')
        print('Total de  MWH, Sopladora:', tot_sopladora_q, 'MWH')
    elif n_ciudad2 == 'Loja':
        print('Total de  MWH, Sopladora:', tot_sopladora_l, 'MWH')
    else:
        print('Ninguna planta otorga energía la ciudad seleccionada')
    print()

    exit


#3. Solicite el nombre de una región al usuario y presente cuento dinero ha recaudado la
#región
elif opcion == '3':
    print('''
          DINERO RECAUDADO REGIONES: Costa, Sierra,  Oriente
    '''),

    n_region = input('Ingrese el nombre de Región: ')

    if n_region == 'Costa':
        print('Total Recaudado en la Región Costa: ', costa, '$')
    elif n_region == 'Sierra':
        print('Total Recaudado en la Región Sierra: ', sierra, '$')
    elif n_region == 'Oriente':
        print(oriente)
    else:
        print("Digite correctamente la primera en mayuscula")
```

