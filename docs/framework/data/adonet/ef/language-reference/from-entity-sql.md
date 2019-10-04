---
title: FROM (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ff3e3048-0d5d-4502-ae5c-9187fcbd0514
ms.openlocfilehash: 2334a30009d6bef9544d2ca1e0ab923a7441d6f2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833824"
---
# <a name="from-entity-sql"></a>FROM (Entity SQL)
Specifica la raccolta usata nelle istruzioni [Select](select-entity-sql.md) .

## <a name="syntax"></a>Sintassi

```sql
FROM expression [ ,...n ] AS C
```

## <a name="arguments"></a>Argomenti

`expression` \
Qualsiasi espressione di query valida che produce una raccolta da usare come origine in un'istruzione `SELECT`.

## <a name="remarks"></a>Note

Una clausola `FROM` è un elenco delimitato da virgole di uno o più elementi della clausola `FROM`. La clausola `FROM` può essere usata per specificare una o più origini per un'istruzione `SELECT`. Il tipo più semplice di clausola `FROM` consiste in una singola espressione di query che identifica una raccolta e un alias usati come origine in un'istruzione `SELECT`, come illustrato nell'esempio seguente:

`FROM C as c`

## <a name="from-clause-items"></a>Elementi della clausola FROM

Ogni elemento della clausola `FROM` si riferisce a una raccolta di origine nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta le classi seguenti di elementi della clausola `FROM`: elementi della clausola `FROM` semplici, elementi della clausola `JOIN FROM` ed elementi della clausola `APPLY FROM` Nelle sezioni seguenti è disponibile una descrizione più dettagliata per ognuno di questi elementi della clausola `FROM`.

### <a name="simple-from-clause-item"></a>Elemento della clausola FROM semplice

L'elemento della clausola `FROM` più semplice è dato da una singola espressione che identifica una raccolta e un alias. L'espressione può consistere semplicemente in un set di entità, o subquery, o in qualsiasi altra espressione corrispondente a un tipo di raccolta. Di seguito è riportato un esempio:

```sql
LOB.Customers as c
```

La specifica dell'alias è facoltativa. Di seguito è riportato un esempio di specifica alternativa per l'elemento della clausola FROM precedente:

```sql
LOB.Customers
```

Se non viene specificato alcun alias, in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene eseguito un tentativo di generare un alias in base all'espressione della raccolta.

### <a name="join-from-clause-item"></a>Elemento della clausola JOIN FROM

Un elemento della clausola `JOIN FROM` rappresenta un join tra due elementi della clausola `FROM`. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta cross join, inner join, left e right outer join e full outer join. Tutti questi join sono supportati in modo analogo al modo in cui sono supportati in Transact-SQL. Come in Transact-SQL, i due elementi della clausola `FROM` che interessano il `JOIN` devono essere indipendenti. In altre parole, non possono essere correlati. In questi casi è possibile usare una clausola `CROSS APPLY` o `OUTER APPLY`.

#### <a name="cross-joins"></a>Cross join

Un'espressione di query `CROSS JOIN` genera il prodotto cartesiano di due raccolte, come illustrato nell'esempio seguente:

`FROM C AS c CROSS JOIN D as d`

#### <a name="inner-joins"></a>Inner join

Un `INNER JOIN` genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:

`FROM C AS c [INNER] JOIN D AS d ON e`

L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera. Se non è specificata alcuna condizione `ON`, un `INNER JOIN` degenera in un `CROSS JOIN`.

#### <a name="left-outer-joins-and-right-outer-joins"></a>Left outer join e right outer join

Un'espressione di query `OUTER JOIN` genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:

`FROM C AS c LEFT OUTER JOIN D AS d ON e`

L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera. Se la condizione `ON` è falsa, l'espressione elabora comunque una sola istanza dell'elemento a sinistra abbinato all'elemento a destra con valore Null.

Un `RIGHT OUTER JOIN` può essere espresso in modo simile.

#### <a name="full-outer-joins"></a>Full Outer Join

Un `FULL OUTER JOIN` esplicito genera un prodotto cartesiano vincolato di due raccolte, come illustrato nell'esempio seguente:

`FROM C AS c FULL OUTER JOIN D AS d ON e`

L'espressione di query precedente elabora una combinazione di ogni elemento della raccolta a sinistra abbinato a ogni elemento della raccolta a destra, in cui la condizione `ON` è vera. Se la condizione `ON` è falsa, l'espressione elabora comunque una sola istanza dell'elemento a sinistra abbinato all'elemento a destra con valore Null. Elabora inoltre una sola istanza dell'elemento a destra abbinato all'elemento a sinistra con valore Null.

> [!NOTE]
> Per mantenere la compatibilità con SQL-92, in Transact-SQL la parola chiave OUTER è facoltativa. Pertanto, `LEFT JOIN`, `RIGHT JOIN` e `FULL JOIN` sono sinonimi di `LEFT OUTER JOIN`, `RIGHT OUTER JOIN` e `FULL OUTER JOIN`.

### <a name="apply-clause-item"></a>Elemento della clausola APPLY

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta due tipi di clausola `APPLY`: `CROSS APPLY` e `OUTER APPLY`.

Una clausola `CROSS APPLY` produce un abbinamento univoco di ogni elemento della raccolta a sinistra con un elemento della raccolta prodotto dalla valutazione dell'espressione a destra. Con una clausola `CROSS APPLY`, l'espressione a destra dipende dal punto di vista funzionale dall'elemento a sinistra, come illustrato nell'esempio di raccolta associata seguente:

`SELECT c, f FROM C AS c CROSS APPLY c.Assoc AS f`

Il comportamento di `CROSS APPLY` è simile a quello dell'elenco di join. Se l'espressione a destra restituisce una raccolta vuota, `CROSS APPLY` non produce abbinamenti per quell'istanza dell'elemento a sinistra.

Una clausola `OUTER APPLY` è simile a una `CROSS APPLY`, ad eccezione del fatto che viene prodotto un abbinamento anche se l'espressione a destra restituisce una raccolta vuota. Di seguito viene riportato un esempio di `OUTER APPLY`.

`SELECT c, f FROM C AS c OUTER APPLY c.Assoc AS f`

> [!NOTE]
> Diversamente da Transact-SQL, non è necessario un passaggio di unnesting esplicito in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].

> [!NOTE]
> gli operatori `CROSS` e `OUTER APPLY` sono stati introdotti nella SQL Server 2005. In alcuni casi, è possibile che la pipeline della query produca istruzioni Transact-SQL contenenti gli operatori `CROSS APPLY` e/o `OUTER APPLY`. Poiché alcuni provider back-end, incluse le versioni di SQL Server precedenti SQL Server 2005, non supportano questi operatori, tali query non possono essere eseguite su questi provider back-end.
>
> Di seguito sono elencati alcuni degli scenari tipici che potrebbero determinare la presenza degli operatori `CROSS APPLY` e/o `OUTER APPLY` nella query di output: una subquery correlata con paging, AnyElement su una subquery correlata o su una raccolta prodotta dalla navigazione, query LINQ che usano metodi di raggruppamento che accettano un selettore elemento, una query nella quale viene specificata in modo esplicito una clausola `CROSS APPLY` o `OUTER APPLY`, una query che presenta un costrutto `DEREF` su un costrutto `REF`.

## <a name="multiple-collections-in-the-from-clause"></a>Più raccolte nella clausola FROM

La clausola `FROM` può contenere più raccolte separate da virgole. In questi casi, si presuppone che le raccolte siano unite in join, come se si trattasse di un CROSS JOIN a n vie.

Nell'esempio seguente `C` e `D` sono raccolte indipendenti, ma `c.Names` dipende da `C`.

```sql
FROM C AS c, D AS d, c.Names AS e
```

L'esempio precedente rappresenta l'equivalente logico dell'esempio seguente.

`FROM (C AS c JOIN D AS d) CROSS APPLY c.Names AS e`

## <a name="left-correlation"></a>Correlazione sinistra
 Gli elementi nella clausola `FROM` possono fare riferimento a elementi specificati nelle clausole precedenti. Nell'esempio seguente `C` e `D` sono raccolte indipendenti, ma `c.Names` è dipendente da `C`:

```sql
from C as c, D as d, c.Names as e
```

Si tratta dell'equivalente logico di:

```sql
from (C as c join D as d) cross apply c.Names as e
```

## <a name="semantics"></a>Semantics

Dal punto di vista logico, si presuppone che le raccolte nella clausola `FROM` facciano parte di un cross join a `n` vie, tranne nel caso di un cross join a una via. Gli alias nella clausola `FROM` vengono elaborati da sinistra verso destra e vengono aggiunti all'ambito corrente per i riferimenti futuri. Si presuppone che la clausola `FROM` produca un multiset di righe. Per ogni elemento della clausola `FROM` sarà presente un campo che rappresenterà un singolo elemento della raccolta in questione.

La clausola `FROM` produce logicamente un multiset di righe di tipo Row(c, d, e) in cui si presuppone che i campi c, d ed e siano del tipo di elemento `C`, `D` e `c.Names`.

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduce nell'ambito un alias per ogni elemento della clausola `FROM` semplice. Nel frammento di clausola FROM seguente, ad esempio, i nomi introdotti nell'ambito sono c, d ed e.

```sql
from (C as c join D as d) cross apply c.Names as e
```

In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (a differenza di Transact-SQL), la clausola `FROM` introduce solo gli alias nell'ambito. Tutti i riferimenti alle colonne, o proprietà, di tali raccolte devono essere qualificati con l'alias.

## <a name="pulling-up-keys-from-nested-queries"></a>Pull delle chiavi da query annidate

Non sono supportati determinati tipi di query che richiedono l'estrazione delle chiavi da una query annidata. Viene ad esempio considerata valida la query seguente:

```sql
select c.Orders from Customers as c
```

L'esempio seguente non è invece considerato valido, in quanto la query annidata non contiene chiavi:

```sql
select {1} from {2, 3}
```

## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Espressioni di query](query-expressions-entity-sql.md)
- [Tipi strutturati nullable](nullable-structured-types-entity-sql.md)
