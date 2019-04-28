---
title: Procedure consigliate per la generazione di SQL dagli alberi dei comandi
ms.date: 03/30/2017
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
ms.openlocfilehash: 6ac46b577f071bca6c79e23b8b77f9b267ac879b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606667"
---
# <a name="generating-sql-from-command-trees---best-practices"></a>Procedure consigliate per la generazione di SQL dagli alberi dei comandi

Gli alberi dei comandi di query di output sono molto simili alle query esprimibili in SQL. Per generare SQL da un albero dei comandi di output, tuttavia i writer del provider devono affrontare alcune difficoltà comuni. In questo argomento vengono illustrate tali difficoltà, mentre nell'argomento successivo il provider di esempio mostra come risolverle.

## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a>Nodi DbExpression di gruppo in un'istruzione SQL SELECT

Un'istruzione SQL tipica presenta una struttura annidata della forma seguente:

```sql
SELECT …
FROM …
WHERE …
GROUP BY …
ORDER BY …
```

Una o più clausole potrebbero essere vuote.  In qualsiasi riga potrebbe essere presente un'istruzione SELECT annidata.

Una possibile conversione di un albero dei comandi delle query in un'istruzione SQL SELECT produrrebbe una sottoquery per ogni operatore relazionale. Ciò comporterebbe tuttavia la creazione di sottoquery annidate non necessarie e di difficile lettura.  Per alcuni archivi dati le prestazioni delle query potrebbero essere scarse.

Si consideri, come esempio, l'albero dei comandi di query seguente

```
Project (
a.x,
   a = Filter(
      b.y = 5,
      b = Scan("TableA")
   )
)
```

Una conversione non efficace produrrebbe:

```sql
SELECT a.x
FROM (   SELECT *
         FROM TableA as b
         WHERE b.y = 5) as a
```

Si osservi come ogni nodo dell'espressione relazionale diventa una nuova istruzione SQL SELECT.

Pertanto, è importante aggregare il maggior numero di nodi dell'espressione possibile in una sola istruzione SQL SELECT senza compromettere la correttezza.

Il risultato di un'aggregazione di questo tipo per l'esempio sopra presentato sarebbe:

```sql
SELECT b.x
FROM TableA as b
WHERE b.y = 5
```

## <a name="flatten-joins-in-a-sql-select-statement"></a>Rendere bidimensionali i join in un'istruzione SQL SELECT

Un caso di aggregazione di più nodi in un'unica istruzione SQL SELECT consiste nell'aggregazione di più espressioni di join in un'unica istruzione SQL SELECT. DbJoinExpression rappresenta un unico join tra due input. È tuttavia possibile specificare più di un join come parte di un'unica istruzione SQL SELECT. In questo caso i join vengono eseguiti nell'ordine specificato.

I join del lato sinistro, ovvero quelli che vengono visualizzati come join figlio a sinistra di un altro join, possono essere più facilmente resi bidimensionali in un'unica istruzione SQL SELECT. Si consideri, come esempio, l'albero dei comandi di query seguente:

```
InnerJoin(
   a = LeftOuterJoin(
   b = Extent("TableA")
   c = Extent("TableB")
   ON b.y = c.x ),
   d = Extent("TableC")
   ON a.b.y = d.z
)
```

Tale struttura può essere convertita correttamente in:

```sql
SELECT *
FROM TableA as b
LEFT OUTER JOIN TableB as c ON b.y = c.x
INNER JOIN TableC as d ON b.y = d.z
```

I join non di sinistra non possono tuttavia essere facilmente resi bidimensionali e non è consigliabile provare a eseguire questa operazione. Ad esempio, i join dell'albero dei comandi di query seguente:

```
InnerJoin(
   a = Extent("TableA")
   b = LeftOuterJoin(
   c = Extent("TableB")
   d = Extent("TableC")
   ON c.y = d.x),
   ON a.z = b.c.y
)
```

Verrebbero convertiti in un'istruzione SQL SELECT con una sottoquery.

```sql
SELECT *
FROM TableA as a
INNER JOIN (SELECT *
   FROM TableB as c
   LEFT OUTER JOIN TableC as d
   ON c.y = d.x) as b
ON b.y = d.z
```

## <a name="input-alias-redirecting"></a>Reindirizzamento degli alias di input

Per comprendere il reindirizzamento degli alias di input, si consideri la struttura delle espressioni relazionali, ad esempio DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression e DbSkipExpression.

Per ognuno di questi tipi sono disponibili una o più proprietà Input che descrivono una raccolta di input e, per rappresentare ogni elemento di tale input durante un attraversamento della raccolta, viene usata una variabile di associazione che corrisponde a ogni input. La variabile di associazione viene usata quando si fa riferimento all'elemento di input, ad esempio nella proprietà Predicate di un oggetto DbFilterExpression o nella proprietà Projection di un oggetto DbProjectExpression.

Quando si aggregano più nodi dell'espressione relazionale in una sola istruzione SQL SELECT e si valuta un'espressione che fa parte di un'espressione relazionale, ad esempio parte della proprietà Projection di un oggetto DbProjectExpression, la variabile di associazione usata potrebbe non corrispondere all'alias dell'input, in quanto più associazioni di espressioni dovrebbero essere reindirizzate a un solo extent.  Questo problema viene definito ridenominazione degli alias.

Si consideri il primo esempio di questo argomento. Se si esegue la conversione semplice e si converte Projection a.x (DbPropertyExpression(a, x)), è corretto convertirlo in `a.x`, in quanto all'input è stato associato l'alias "a" per creare corrispondenza con la variabile di associazione.  Quando tuttavia si aggregano entrambi i nodi in un'unica istruzione SQL SELECT, è necessario convertire lo stesso oggetto DbPropertyExpression in `b.x`, in quanto all'input è stato associato l'alias "b".

## <a name="join-alias-flattening"></a>Bidimensionalità degli alias di join

A differenza di qualsiasi altra espressione relazionale di un albero dei comandi di output, DbJoinExpression restituisce un tipo di risultato costituito da una riga formata da due colonne, ognuna delle quali corrisponde a uno degli input. Quando un oggetto DbPropertyExpression viene compilato per accedere a una proprietà scalare proveniente da un join, viene eseguita su un altro oggetto DbPropertyExpression.

Gli esempi includono "a.b.y" nell'esempio 2 e "b.c.y" nell'esempio 3. Nelle istruzioni SQL corrispondenti tuttavia vi si fa riferimento come a "b.y". Questa nuova assegnazione degli alias viene denominata bidimensionalità degli alias di join.

## <a name="column-name-and-extent-alias-renaming"></a>Ridenominazione dei nomi di colonna e degli alias degli extent

Se è necessario completare con una proiezione una query SQL SELECT che presenta un join, quando si enumerano tutte le colonne coinvolte dagli input, è possibile che si verifichi un conflitto di nomi, in quanto più input potrebbero avere lo stesso nome di colonna. Usare un nome diverso per la colonna per evitare il conflitto.

Inoltre, quando si rendono bidimensionali i join, è possibile che si verifichi un conflitto tra gli alias delle tabelle coinvolte (o sottoquery). In questo caso, è necessario rinominarle.

## <a name="avoid-select-"></a>Evitare SELECT *

Non usare `SELECT *` per effettuare la selezione dalle tabelle di base. Il modello di archiviazione in un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] applicazione può includere solo un subset delle colonne che sono nella tabella di database. In questo caso, è possibile che `SELECT *` produca un risultato errato. Al contrario, è necessario specificare tutte le colonne coinvolte tramite i nomi di colonna del tipo di risultato delle espressioni interessate.

## <a name="reuse-of-expressions"></a>Riutilizzo delle espressioni

È possibile riutilizzare le espressioni nell'albero dei comandi di query passato da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Non presupporre che ogni espressione sia visualizzata solo una volta nell'albero dei comandi di query.

## <a name="mapping-primitive-types"></a>Mapping di tipi primitivi

Quando si esegue il mapping di tipi concettuali (EDM) ai tipi di provider, è necessario eseguire il mapping al tipo più ampio (Int32), in modo che sia possibile adattare tutti i valori possibili. Inoltre, evitare di mapping a tipi non possono essere usati per molte operazioni, come i tipi BLOB (ad esempio, `ntext` in SQL Server).

## <a name="see-also"></a>Vedere anche

- [Generazione SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
