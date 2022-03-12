# consumo-de-energia-

Para administrar la nueva matriz energética del Ecuador, Ud. tiene un diccionario con la información de las
plantas de energía y a las ciudades que atienden. Cada ciudad tiene: una tupla con los consumos mensuales
(12) del año en megavatios-hora (MWh) y la tarifa de consumo en dólares por megavatio-hora (MWh) que le
cobra la planta eléctrica. Una ciudad puede estar servida por más de una planta eléctrica. No todas las
ciudades son servidas por todas las plantas eléctricas.

```python
consumo_energia = {
    'Coca Codo Sinclair':{
        'Quito': {'consumos': (400, 432, 400, 420, 432, 460, 432, 400, 432, 300, 213, 400), 'tarifa': 65}
    }
}

tarifa_coca_quito = consumo_energia['Coca Codo Sinclair']['Quito']['tarifa']
consumos_coca_quito = consumo_energia['Coca Codo Sinclair']['Quito']['consumos']

print(consumo_energia['Coca Codo Sinclair']['Quito']['consumos'][3])
print(consumo_energia['Coca Codo Sinclair']['Quito']['consumos'][11])
print(consumo_energia['Coca Codo Sinclair']['Quito']['tarifa'])
print(tarifa_coca_quito * consumos_coca_quito[11])

print(consumos_coca_quito)

consumo = 0
for c in consumos_coca_quito:
    consumo += c

print('Consumo total:', consumo)

```
