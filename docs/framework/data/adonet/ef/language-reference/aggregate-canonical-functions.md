---
title: Funzioni di aggregazione canoniche
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 04b7d9c20373a465c073d55a090f1c2fd7fc6e07
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="aggregate-canonical-functions"></a>Funzioni di aggregazione canoniche

Le aggregazioni sono espressioni che riducono una serie di valori di input, ad esempio, in un singolo valore. In genere, vengono usate insieme alla clausola GROUP BY dell'espressione SELECT. Il relativo uso è tuttavia soggetto ad alcuni vincoli.

Nella tabella seguente sono illustrate le funzioni canoniche di aggregazione [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

| Funzione | Descrizione |
| -------- | ----------- |
| `Avg(expression)` | Restituisce la media dei valori non Null.<br><br>**Argomenti**<br><br>Un `Int32`, `Int64`, `Double`, e `Decimal`.<br><br>**Valore restituito**<br><br>Tipo di `expression`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)] [!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)] |
| `BigCount(expression)` | Restituisce la dimensione dell'aggregazione, inclusi i valori Null e duplicati.<br><br>**Argomenti**<br><br>Qualsiasi tipo.<br><br>**Valore restituito**<br><br>Oggetto `Int64`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)] [!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)] |
| `Count(expression)` | Restituisce la dimensione dell'aggregazione, inclusi i valori Null e duplicati.<br><br>**Argomenti**<br><br>Qualsiasi tipo.<br><br>**Valore restituito**<br><br>Oggetto `Int32`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)] [!code-sql[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)] |
| `Max(expression)` | Restituisce il numero massimo di valori non Null.<br><br>**Argomenti**<br><br>Valore `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br><br>**Valore restituito**<br><br>Tipo di `expression`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)] [!code-sql[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)] |
| `Min(expression)` | Restituisce il numero minimo di valori non Null.<br><br>**Argomenti**<br><br>Valore `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br><br>**Valore restituito**<br><br>Tipo di `expression`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)] [!code-sql[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)] |
| `StDev(expression)` | Restituisce la deviazione standard dei valori non Null.<br><br>**Argomenti**<br><br>Valore `Int32`, `Int64`, `Double`, `Decimal`.<br><br>**Valore restituito**<br><br>Oggetto `Double`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)] [!code-sql[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)] |
| `StDevP(expression)` | Restituisce la deviazione standard della popolazione di tutti i valori.<br><br>**Argomenti**<br><br>Valore `Int32`, `Int64`, `Double`, `Decimal`.<br><br>**Valore restituito**<br><br>Oggetto `Double`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)] [!code-sql[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)] |
| `Sum(expression)` | Restituisce la somma dei valori non Null.<br><br>**Argomenti**<br><br>Valore `Int32`, `Int64`, `Double`, `Decimal`.<br><br>**Valore restituito**<br><br>Oggetto `Double`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)] [!code-sql[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)] |
| `Var(expression)` | Restituisce la varianza di tutti i valori non Null.<br><br>**Argomenti**<br><br>Valore `Int32`, `Int64`, `Double`, `Decimal`.<br><br>**Valore restituito**<br><br>Oggetto `Double`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)] [!code-sql[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)] |
| `VarP(expression)` | Restituisce la varianza della popolazione di tutti i valori non Null.<br><br>**Argomenti**<br><br>Valore `Int32`, `Int64`, `Double`, `Decimal`.<br><br>**Valore restituito**<br><br>Oggetto `Double`. `Null`, se tutti i valori di input sono valori `null`.<br><br>**Esempio**[!code-csharp[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)] [!code-sql[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] |

Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL. Per ulteriori informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Aggregazioni basate sulle raccolte

Le aggregazioni basate su raccolte (funzioni della Collection) operano sulle raccolte e restituiscono un valore. Ad esempio se ORDERS è una raccolta di tutti gli ordini, è possibile calcolare la prima data di spedizione con l'espressione seguente:

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

Le espressioni all'interno di aggregazioni basate su raccolte vengono valutate nell'ambito di risoluzione dei nomi di ambiente corrente.

## <a name="group-based-aggregates"></a>Aggregazioni basate su gruppo

Le aggregazioni basate su gruppo vengono calcolate su un gruppo definito dalla clausola GROUP BY. Per ogni gruppo nel risultato viene calcolata un'aggregazione distinta usando gli elementi in ciascun gruppo come input nel calcolo dell'aggregazione. Quando in un'espressione selezionata viene usata una clausola GROUP BY, nella proiezione o nella clausola ORDER BY possono essere presenti solo nomi di espressioni di raggruppamento, aggregazioni o espressioni costanti.

Nell'esempio seguente viene calcolata la quantità media ordinata per ciascun prodotto:

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

È possibile disporre di un'aggregazione basata su gruppo senza una clausola group by esplicita nell'espressione SELECT. In questo caso, tutti gli elementi vengono considerati un unico gruppo. Questo è equivalente della specifica di un raggruppamento basato su una costante. Si consideri, ad esempio, l'espressione seguente:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

L'espressione equivale alla seguente:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Le espressioni all'interno dell'aggregazione basata su gruppo vengono valutate nell'ambito della risoluzione dei nomi visibile per l'espressione della clausola WHERE.

Come in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], aggregazioni basate su gruppo è possono specificare anche un ALL o DISTINCT modificatore. Se è specificato il modificatore DISTINCT, eventuali duplicati vengono eliminati dalla raccolta di input di aggregazione prima del calcolo dell'aggregazione. Se è specificato il modificatore ALL o se non è specificato alcun modificatore, non viene eseguita l'eliminazione dei duplicati.  

## <a name="see-also"></a>Vedere anche

[Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
