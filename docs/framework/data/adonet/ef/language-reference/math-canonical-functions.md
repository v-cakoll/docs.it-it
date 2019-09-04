---
title: Funzioni matematiche canoniche
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9417ff9836912017c9d88bb24a18849aaac2836a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250313"
---
# <a name="math-canonical-functions"></a>Funzioni matematiche canoniche

Entity SQL include le funzioni canoniche matematiche seguenti:
  
## <a name="absvalue"></a>Abs(value)

Restituisce il valore assoluto di `value`.

**Argomenti**

`Int16` ,`Int32` ,,`Single`,, E.`Double` `Byte` `Int64` `Decimal`

**Valore restituito**

Tipo di `value`.

**Esempio**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling(value)

Restituisce il valore integer più piccolo non minore di `value`.

**Argomenti**

`Single` ,`Double`E .`Decimal`

**Valore restituito**

Tipo di `value`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor(value)

Restituisce il valore integer più grande non maggiore di `value`.

**Argomenti**

`Single` ,`Double`E .`Decimal`

**Valore restituito**

Tipo di `value`.

**Esempio**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(value, exponent)

Restituisce il risultato dell'oggetto `value` specificato all'oggetto `exponent` specificato.

**Argomenti**

|  |  |
|--|--|
|`value` | Oggetto `Int32, Int64, Double`o .`Decimal` |
|`exponent` | Oggetto `Int64`, `Double`o .`Decimal` |

**Valore restituito**

Tipo di `value`.

**Esempio**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round(value)

Restituisce la parte intera di `value` arrotondata al valore integer più vicino.

**Argomenti**

`Single` ,`Double`E .`Decimal`

**Valore restituito**

Tipo di `value`.

**Esempio**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(value, digits)

Restituisce `value`, arrotondato al valore di `digits` specificato più vicino.

**Argomenti**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valore restituito**

Tipo di `value`.

**Esempio**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(value, digits)

Restituisce `value`, troncato al valore di `digits` specificato più vicino.

**Argomenti**

|  |  |
|--|--|
|`value`|`Double` o `Decimal`.|
|`digits`|`Int16` o `Int32`.|

**Valore restituito**

Tipo di `value`.

**Esempio**

`Truncate(748.58,1)`  
  
 Queste funzioni restituiscono `null` se l'input è `null`.  
  
 Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL. Per ulteriori informazioni, vedere [SqlClient per le funzioni Entity Framework](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni canoniche](canonical-functions.md)
