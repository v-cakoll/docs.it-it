---
title: GROUP BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 711fbdc2d51177037cf349150c3431de14b11974
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833786"
---
# <a name="group-by-entity-sql"></a>GROUP BY (Entity SQL)
Specifica i gruppi nei quali devono essere inseriti gli oggetti restituiti da un'espressione ([SELECT](select-entity-sql.md)) di query.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `aliasedExpression`  
 Qualsiasi espressione di query valida sulla quale viene eseguito il raggruppamento. `expression` può essere una proprietà o un'espressione non di aggregazione che fa riferimento a una proprietà restituita dalla clausola FROM. Ogni espressione in una clausola GROUP BY deve restituire un tipo che può essere confrontato per verificare l'uguaglianza. Questi tipi sono in genere tipi primitivi scalari ad esempio numeri, stringhe e date. Non è possibile eseguire un raggruppamento in base a una raccolta.  
  
## <a name="remarks"></a>Note  
 Se le funzioni di aggregazione sono incluse nella clausola SELECT \<select list >, GROUP BY calcola un valore di riepilogo per ogni gruppo. Quando si specifica GROUP BY, è necessario che l'elenco GROUP BY includa ogni nome di proprietà di qualsiasi espressione non di aggregazione nell'elenco di selezione oppure che l'espressione GROUP BY corrisponda esattamente all'espressione dell'elenco di selezione.  
  
> [!NOTE]
> Se la clausola ORDER BY non viene specificata, i gruppi restituiti dalla clausola GROUP BY non sono in un ordine preciso. Per specificare un particolare ordinamento dei dati, è consigliabile usare sempre la clausola ORDER BY.  
  
 Quando una clausola GROUP BY viene specificata, in modo esplicito o implicito (ad esempio da una clausola HAVING nella query), l'ambito corrente viene nascosto e viene introdotto un nuovo ambito.  
  
 La clausola SELECT, la clausola HAVING e la clausola ORDER BY non potranno più fare riferimento ai nomi di elementi specificati nella clausola FROM. È possibile fare riferimento solo alle espressioni di raggruppamento stesse. A tale scopo, è possibile assegnare nuovi nomi (alias) a ogni espressione di raggruppamento. Se per un'espressione di raggruppamento non viene specificato alcun alias, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generarne uno usando le regole di generazione di alias, come illustrato nell'esempio seguente.  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 Le espressioni nella clausola GROUP BY non possono fare riferimento a nomi definiti in precedenza nella stessa clausola GROUP BY.  
  
 Oltre ai nomi dei raggruppamenti, nella clausola SELECT, nella clausola HAVING e nella clausola ORDER BY è possibile specificare anche aggregazioni. Un'aggregazione contiene un'espressione valutata per ogni elemento del gruppo. L'operatore di aggregazione riduce i valori di tutte queste espressioni, in genere, ma non sempre, in un singolo valore. L'espressione di aggregazione può fare riferimento ai nomi degli elementi originali visibili nell'ambito padre o ai nuovi nomi introdotti dalla clausola GROUP BY stessa. Sebbene le aggregazioni siano presenti nella clausola SELECT, nella clausola HAVING e nella clausola ORDER BY, vengono effettivamente valutate nello stesso ambito delle espressioni di raggruppamento, come illustrato nell'esempio seguente.  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 In questa query viene usata la clausola GROUP BY per produrre un rapporto del costo di tutti i prodotti ordinati, suddiviso in base al prodotto. Viene assegnato il nome `name` al prodotto come parte dell'espressione di raggruppamento, quindi viene fatto riferimento a tale nome nell'elenco SELECT. Viene inoltre specificata la funzione `sum` di aggregazione nell'elenco SELECT, che fa riferimento internamente al prezzo e alla quantità della riga dell'ordine.  
  
 Ogni espressione chiave GROUP BY deve includere almeno un riferimento all'ambito di input:  
  
```sql  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 Per un esempio dell'uso di GROUP BY, vedere [HAVING](having-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore GROUP BY per specificare i gruppi in cui gli oggetti vengono restituiti da una query. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di PrimitiveType @ no__t-0.  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#GROUPBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#groupby)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Espressioni di query](query-expressions-entity-sql.md)
