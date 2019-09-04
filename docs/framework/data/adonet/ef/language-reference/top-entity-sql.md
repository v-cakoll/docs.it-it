---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 8b55519b7f95deb6463af4c0a6a2a53975e5b5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248981"
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)

La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo. La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query.

## <a name="syntax"></a>Sintassi

```
[ TOP (n) ]
```

## <a name="arguments"></a>Argomenti

`n`Espressione numerica che specifica il numero di righe da restituire. `n` potrebbero essere un singolo valore letterale numerico o un singolo parametro.

## <a name="remarks"></a>Note

L'espressione TOP deve essere un singolo valore letterale numerico o un singolo parametro. Se viene usato un valore letterale costante, il tipo del valore letterale deve essere implicitamente promuovibile a Edm.Int64 (byte, int16, int32 o int64 oppure qualsiasi tipo di provider mappato a un tipo promuovibile a Edm.Int64) e il suo valore deve essere maggiore o uguale a zero. In caso contrario, viene generata un'eccezione. Se come espressione viene usato un parametro, anche il tipo di parametro deve essere implicitamente promuovibile a Edm.Int64, ma non verrà eseguita alcuna convalida effettiva del valore del parametro durante la compilazione in quanto per i valori dei parametri viene usata l'associazione tardiva.

Di seguito è illustrato un esempio di espressione TOP costante.

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

Di seguito è riportato un esempio di espressione TOP con parametri:

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

L'espressione TOP non è deterministica, a meno che la query non venga ordinata. Se è necessario un risultato deterministico, usare le sottoclausole [SKIP](skip-entity-sql.md) e [LIMIT](limit-entity-sql.md) nella clausola [ORDER BY](order-by-entity-sql.md) . TOP e SKIP/LIMIT si escludono a vicenda.

## <a name="example"></a>Esempio

Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato TOP per specificare la riga superiore da restituire dal risultato della query. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:

1. Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.

2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :

    [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]

## <a name="see-also"></a>Vedere anche

- [SELECT](select-entity-sql.md)
- [SKIP](skip-entity-sql.md)
- [LIMIT](limit-entity-sql.md)
- [ORDER BY](order-by-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
