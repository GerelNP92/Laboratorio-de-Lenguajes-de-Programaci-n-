# Tarea 1 - Laboratorio de Lenguajes de Programación I

## Información del Estudiante

- **Nombre:** Gerel Enrique, Negreira Peruzzi
- **Carnet:** 09-11163
- **Universidad:** Universidad Simón Bolívar
- **Materia:** CI-3661 - Laboratorio de Lenguajes de Programación I
- **Período:** Septiembre - Diciembre 2025

---

## Descripción

Esta tarea consiste en la implementación de 6 problemas en Haskell que cubren diferentes aspectos del lenguaje funcional:

1. **Palíndromo** - Recursión explícita
2. **Producto de Pares** - Recursión con filtrado
3. **Parseo Condicional** - Manejo de Either y Maybe
4. **Suma Acumulada** - Uso de filter y fold
5. **Coordenadas Impares** - Listas por comprensión
6. **Descomposición Segura** - Manejo seguro con Maybe

---



## Ejecución

### Ejecutar el Programa Principal

```bash
stack run
```

### Ejecutar las Pruebas Unitarias

```bash
stack test
```

### Compilación Manual (alternativa)

```bash
# Compilar Tarea1.hs
ghc -o tarea1 src/Tarea1.hs

# Compilar y ejecutar tests
ghc --make test/Test.hs -isrc
./test/Test
```

---

