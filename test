-------------------------------------------------------------------------------
-- Tests.hs - Pruebas Unitarias para Tarea 1
-- Usa el framework HUnit. Para compilar y correr:
-- 1. Asegúrate de tener la librería HUnit instalada (e.g., usando cabal o stack).
-- 2. Compila: ghc --make Tests.hs
-- 3. Ejecuta: ./Tests
-------------------------------------------------------------------------------

module Main where

import Tarea1
import Test.HUnit
import Data.Char (toUpper)

-------------------------------------------------------------------------------
-- 1. Pruebas para esPalindromo
-------------------------------------------------------------------------------

testsPalindromo :: Test
testsPalindromo = TestList
    [ "Palíndromo simple" ~: esPalindromo "oso" ~?= True
    , "Palíndromo vacío" ~: esPalindromo "" ~?= True
    , "Palíndromo un carácter" ~: esPalindromo "a" ~?= True
    , "Palíndromo largo" ~: esPalindromo "anitalavalatina" ~?= True
    , "No palíndromo" ~: esPalindromo "hola" ~?= False
    , "Palíndromo par" ~: esPalindromo "abba" ~?= True
    , "Palíndromo impar" ~: esPalindromo "radar" ~?= True
    ]

-------------------------------------------------------------------------------
-- 2. Pruebas para productoParesRec
-------------------------------------------------------------------------------

testsProductoParesRec :: Test
testsProductoParesRec = TestList
    [ "Solo pares" ~: productoParesRec [2, 4, 6] ~?= 48
    , "Lista vacía" ~: productoParesRec [] ~?= 1
    , "Solo impares" ~: productoParesRec [1, 3, 5] ~?= 1
    , "Mezcla pares e impares" ~: productoParesRec [1, 2, 3, 4, 5] ~?= 8
    , "Un solo par" ~: productoParesRec [2] ~?= 2
    , "Con cero" ~: productoParesRec [2, 0, 4] ~?= 0
    , "Negativos pares" ~: productoParesRec [-2, -4] ~?= 8
    ]

-------------------------------------------------------------------------------
-- 3. Pruebas para parsearCondicional
-------------------------------------------------------------------------------

testsParsearCondicional :: Test
testsParsearCondicional = TestList
    [ "Solo números válidos" ~: parsearCondicional ["42"] ~?= [Right 42]
    , "Solo texto" ~: parsearCondicional ["hola"] ~?= [Left "HOLA"]
    , "Mezcla" ~: parsearCondicional ["42", "hola", "123"] ~?= [Right 42, Left "HOLA", Right 123]
    , "Lista vacía" ~: parsearCondicional [] ~?= []
    , "Número negativo" ~: parsearCondicional ["-5"] ~?= [Right (-5)]
    , "Texto con números" ~: parsearCondicional ["12abc"] ~?= [Left "12ABC"]
    , "Espacios" ~: parsearCondicional ["  42  "] ~?= [Right 42]
    ]

-------------------------------------------------------------------------------
-- 4. Pruebas para sumaAcumuladaCondicional
-------------------------------------------------------------------------------

testsSumaCondicional :: Test
testsSumaCondicional = TestList
    [ "Umbral 5.0, todos mayores" ~: sumaAcumuladaCondicional 5.0 [6.0, 7.0, 8.0] ~?= 21.0
    , "Umbral 5.0, todos menores" ~: sumaAcumuladaCondicional 5.0 [1.0, 2.0, 3.0] ~?= 0.0
    , "Umbral 5.0, mezcla" ~: sumaAcumuladaCondicional 5.0 [3.0, 6.0, 4.0, 8.0] ~?= 14.0
    , "Lista vacía" ~: sumaAcumuladaCondicional 5.0 [] ~?= 0.0
    , "Umbral 0.0" ~: sumaAcumuladaCondicional 0.0 [1.0, 2.0, 3.0] ~?= 6.0
    , "Números negativos" ~: sumaAcumuladaCondicional (-5.0) [-3.0, -1.0, 2.0] ~?= 1.0
    ]

-------------------------------------------------------------------------------
-- 5. Pruebas para coordenadasImpares
-------------------------------------------------------------------------------

testsCoordenadasImpares :: Test
testsCoordenadasImpares = TestList
    [ "N=1" ~: coordenadasImpares 1 ~?= []
    , "N=2" ~: coordenadasImpares 2 ~?= [(1, 2), (2, 1)]
    , "N=3" ~: length (coordenadasImpares 3) ~?= 4
    , "N=3 contenido" ~: coordenadasImpares 3 ~?= [(1, 2), (1, 4), (2, 1), (2, 3), (3, 2), (3, 4)]
    , "N=0" ~: coordenadasImpares 0 ~?= []
    ]

-- Corrección: Para N=3, el rango es [1..3], entonces las coordenadas son:
-- (1,2) suma=3 impar ✓
-- (2,1) suma=3 impar ✓
-- (2,3) suma=5 impar ✓
-- (3,2) suma=5 impar ✓
-- Total: 4 pares

testsCoordenadasImparesCorregido :: Test
testsCoordenadasImparesCorregido = TestList
    [ "N=1" ~: coordenadasImpares 1 ~?= []
    , "N=2" ~: coordenadasImpares 2 ~?= [(1, 2), (2, 1)]
    , "N=3 cantidad" ~: length (coordenadasImpares 3) ~?= 4
    , "N=3 contenido" ~: coordenadasImpares 3 ~?= [(1, 2), (2, 1), (2, 3), (3, 2)]
    , "N=0" ~: coordenadasImpares 0 ~?= []
    ]

-------------------------------------------------------------------------------
-- 6. Pruebas para descomponerListaSegura
-------------------------------------------------------------------------------

testsDescomponerListaSegura :: Test
testsDescomponerListaSegura = TestList
    [ "Un elemento" ~: descomponerListaSegura [1] ~?= Just (1, [])
    , "Lista vacía" ~: descomponerListaSegura ([] :: [Int]) ~?= Nothing
    , "Múltiples elementos" ~: descomponerListaSegura [1, 2, 3] ~?= Just (1, [2, 3])
    , "Lista de strings" ~: descomponerListaSegura ["hola", "mundo"] ~?= Just ("hola", ["mundo"])
    , "Dos elementos" ~: descomponerListaSegura [5, 10] ~?= Just (5, [10])
    ]

-------------------------------------------------------------------------------
-- Ejecución Principal
-------------------------------------------------------------------------------

-- Lista principal de todos los tests
allTests :: Test
allTests = TestList
    [ TestLabel "Problema 1: esPalindromo" testsPalindromo
    , TestLabel "Problema 2: productoParesRec" testsProductoParesRec
    , TestLabel "Problema 3: parsearCondicional" testsParsearCondicional
    , TestLabel "Problema 4: sumaAcumuladaCondicional" testsSumaCondicional
    , TestLabel "Problema 5: coordenadasImpares" testsCoordenadasImparesCorregido
    , TestLabel "Problema 6: descomponerListaSegura" testsDescomponerListaSegura
    ]

main :: IO Counts
main = do
    putStrLn "==================================================="
    putStrLn "  Ejecutando Pruebas Unitarias - Tarea 1 Haskell"
    putStrLn "==================================================="
    putStrLn ""
    runTestTT allTests
