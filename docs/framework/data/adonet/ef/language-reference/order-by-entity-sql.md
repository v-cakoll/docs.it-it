---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 1233971b172079aa48227d0ec520068afbdf0952
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150069"
---
# <a name="order-by-entity-sql"></a>ORDER BY (Entity SQL)
Specifica il tipo di ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
[ ORDER BY
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]
]  
```  
  
## <a name="arguments"></a>Argomenti  
 `order_by_expression`  
 Qualsiasi espressione di query valida che specifica una proprietà in base a cui eseguire l'ordinamento. È possibile specificare più espressioni di ordinamento. La sequenza delle espressioni di ordinamento nella clausola ORDER BY definisce l'organizzazione del set di risultati ordinato.  
  
 COLLATE {collation_name}  
 Indica che l'operazione ORDER BY deve essere eseguita in base alle regole di confronto specificate in `collation_name`. È possibile applicare COLLATE solo alle espressioni stringa.  
  
 ASC  
 Specifica che i valori nella proprietà specificata devono essere ordinati in modo crescente, dal valore più basso a quello più alto. Questa è la modalità predefinita.  
  
 DESC  
 Specifica che i valori nella proprietà specificata devono essere ordinati in modo decrescente, dal valore più alto a quello più basso.  
  
 LIMIT `n`  
 Verranno selezionati solo i primi `n` elementi.  
  
 SKIP `n`  
 I primi `n` elementi verranno ignorati.  
  
## <a name="remarks"></a>Osservazioni  
 La clausola ORDER BY viene applicata logicamente al risultato della clausola SELECT. La clausola ORDER BY può fare riferimento agli elementi nell'elenco di selezione tramite i relativi alias. La clausola ORDER BY può fare riferimento anche ad altre variabili attualmente incluse nell'ambito. Se, tuttavia, la clausola SELECT è stata specificata con un modificatore DISTINCT, la clausola ORDER BY può fare riferimento solo agli alias della clausola SELECT.  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 Ogni espressione nella clausola ORDER BY deve restituire un tipo che possa essere confrontato per verificare la disuguaglianza ordinata (minore di o maggiore di e così via). Questi tipi sono in genere tipi primitivi scalari ad esempio numeri, stringhe e date. Anche i tipi RowTypes di tipi confrontabili possono essere confrontati in termini di ordinamento.  
  
 Se il codice scorre un set ordinato, non è garantito che l'ordine venga mantenuto, ad eccezione del caso di una proiezione di livello principale.  

Nell'esempio seguente, l'ordine è garantito per essere mantenuto:

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

Nella query seguente, l'ordinamento della query nidificata viene ignorato:  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 Per eseguire un'operazione UNION, UNION ALL, EXCEPT o INTERSECT ordinata, usare il modello seguente:  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a>Parole chiave con restrizioni  
 Le parole chiave seguenti devono essere racchiuse tra virgolette quando usate in una clausola `ORDER BY` :  
  
- CROSS  
  
- FULL  
  
- KEY  
  
- LEFT  
  
- ORDER  
  
- OUTER  
  
- RIGHT  
  
- ROW  
  
- VALORE  
  
## <a name="ordering-nested-queries"></a>Ordinamento di query annidate  
 In Entity Framework un'espressione annidata può essere inserita in una posizione qualsiasi nella query. L'ordine di una query annidata non viene mantenuto.  

La query seguente ordinerà i risultati in base al cognome:  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

Nella query seguente, l'ordinamento della query nidificata viene ignorato:  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ORDER BY per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni di queryQuery Expressions](query-expressions-entity-sql.md)
- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Saltare](skip-entity-sql.md)
- [Limite](limit-entity-sql.md)
- [Torna all'inizio](top-entity-sql.md)
