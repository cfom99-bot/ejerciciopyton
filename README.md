menu = [
    ["Hamburguesa Clásica", "Comida", 25000],
    ["Papas Fritas", "Acompañamiento", 4500],
    ["Pizza Familiar", "Comida", 25000],
    ["Jugo Natural", "Bebida", 3500],
    ["Pastel de Chocolate", "Postre", 6000],
    ["Cerveza ", "Bebida", 5500]
]

def calcular_precio_final(producto, categoria_objetivo, umbral_precio):
    """
    Calcula el precio final aplicando un 15% de descuento si cumple las condiciones.
    """
    nombre, categoria, precio_base = producto
    

    if categoria == categoria_objetivo and precio_base > umbral_precio:
        descuento = precio_base * 0.15
        precio_final = precio_base - descuento
    else:
        precio_final = precio_base
        
    return precio_final


CATEGORIA_PROMO = "Comida"
UMBRAL_PROMO = 10.0

print(f"--- APLICANDO PROMOCIÓN (Categoría: {CATEGORIA_PROMO} | Umbral > ${UMBRAL_PROMO}) ---")
print(f"{'Producto':<22} | {'Categoría':<15} | {'Precio Base':<12} | {'Precio Final':<12}")
print("-" * 70)

for producto in menu:
    nombre, categoria, precio_base = producto
    
    precio_final = calcular_precio_final(producto, CATEGORIA_PROMO, UMBRAL_PROMO)
    
    print(f"{nombre:<22} | {categoria:<15} | ${precio_base:<11.2f} | ${precio_final:<11.2f}")
