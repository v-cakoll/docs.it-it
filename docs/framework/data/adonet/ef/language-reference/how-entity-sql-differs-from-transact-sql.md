---
title: Differenze tra Entity SQL e Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 96e2283074b6c69e51bb7fee4d4f257cdb58d615
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615631"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Differenze di Entity SQL rispetto a Transact-SQL

Questo articolo descrive le differenze tra Entity SQL e Transact-SQL.  
  
## <a name="inheritance-and-relationships-support"></a>Supporto di ereditarietà e relazioni  
 Entity SQL funziona direttamente con gli schemi di entità concettuali e supporta le funzionalità del modello concettuale, ad esempio l'ereditarietà e le relazioni.  
  
 Quando si usa l'ereditarietà, è spesso utile selezionare le istanze di un sottotipo da una raccolta di istanze di supertipi. L'operatore [OfType](oftype-entity-sql.md) in Entity SQL (simile a `oftype` nelle sequenze C#) fornisce questa funzionalità.  
  
## <a name="support-for-collections"></a>Supporto per le raccolte  
 Entity SQL considera le raccolte come entità di prima classe. Ad esempio:  
  
- Le espressioni della Collection sono valide in una clausola `from`.  
  
- Le sottoquery `in` e `exists` sono state generalizzate per consentire qualsiasi raccolta.  
  
     Una sottoquery è un tipo di raccolta. `e1 in e2`e `exists(e)` sono i costrutti di Entity SQL per eseguire queste operazioni.  
  
- Le operazioni Set, ad esempio `union`, `intersect` ed `except`, possono ora essere usate sulle raccolte.  
  
- I join funzionano sulle raccolte.  
  
## <a name="support-for-expressions"></a>Supporto per le espressioni  
 Transact-SQL include sottoquery (tabelle) ed espressioni (righe e colonne).  
  
 Per supportare raccolte e raccolte nidificate, Entity SQL rende ogni elemento un'espressione. Entity SQL è più componibile rispetto a Transact-SQL, ogni espressione può essere usata ovunque. Le espressioni di query restituiscono sempre raccolte dei tipi previsti e possono essere usate in qualunque posizione in cui è consentita un'espressione sulle raccolte. Per informazioni sulle espressioni Transact-SQL non supportate in Entity SQL, vedere [espressioni](unsupported-expressions-entity-sql.md)non supportate.  
  
 Di seguito sono riportate tutte le query di Entity SQL valide:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Modalità di gestione uniforme delle sottoquery  
 Data l'enfasi sulle tabelle, Transact-SQL esegue l'interpretazione contestuale delle sottoquery. Una sottoquery nella clausola, ad esempio, `from` viene considerata come multiset (tabella). La stessa sottoquery usata nella clausola `select` viene invece considerata come una sottoquery scalare. Analogamente, una sottoquery utilizzata sul lato sinistro di un `in` operatore viene considerata una sottoquery scalare, mentre il lato destro dovrebbe essere una sottoquery multiset.  
  
 Entity SQL Elimina queste differenze. Un'espressione dispone di un'interpretazione uniforme che non dipende dal contesto in cui viene usata. Entity SQL considera tutte le sottoquery come sottoquery multiset. Se si desidera un valore scalare dalla sottoquery, Entity SQL fornisce l' `anyelement` operatore che opera su una raccolta (in questo caso, la sottoquery) ed estrae un valore singleton dalla raccolta.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Eliminazione della presenza di coercizioni implicite per le sottoquery  
 Un effetto collaterale della modalità di gestione uniforme delle sottoquery è la conversione implicita delle sottoquery in valori scalari. In particolare, in Transact-SQL, un multiset di righe (con un singolo campo) viene convertito in modo implicito in un valore scalare il cui tipo di dati è quello del campo.  
  
 Entity SQL non supporta questa coercizione implicita. Entity SQL fornisce l' `ANYELEMENT` operatore per estrarre un valore singleton da una raccolta e una `select value` clausola per evitare di creare un wrapper di riga durante un'espressione di query.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>SELECT VALUE: eliminazione della presenza del wrapper di riga implicito  
 La clausola SELECT in una sottoquery Transact-SQL crea in modo implicito un wrapper di riga intorno agli elementi nella clausola. Questo implica che non si possono creare raccolte di scalari o oggetti. Transact-SQL consente una coercizione implicita tra un oggetto `rowtype` con un campo e un valore singleton dello stesso tipo di dati.  
  
 Entity SQL fornisce la `select value` clausola per ignorare la costruzione di riga implicita. Nella clausola `select value` è possibile specificare un solo elemento. Quando si utilizza tale clausola, non viene costruito alcun wrapper di riga intorno agli elementi nella `select` clausola ed è possibile che venga generata una raccolta della forma desiderata, ad esempio `select value a` .  
  
 Entity SQL fornisce anche il costruttore Row per costruire righe arbitrarie. `select`accetta uno o più elementi nella proiezione e restituisce un record di dati con campi:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Correlazione sinistra e utilizzo di alias  
 In Transact-SQL le espressioni in un determinato ambito (una singola clausola come `select` o `from` ) non possono fare riferimento a espressioni definite in precedenza nello stesso ambito. Alcuni dialetti di SQL (incluso Transact-SQL) supportano formati limitati di questi nella `from` clausola.  
  
 Entity SQL generalizza le correlazioni a sinistra nella `from` clausola e le gestisce in modo uniforme. Le espressioni nella clausola `from` possono fare riferimento a definizioni precedenti (definizioni a sinistra) nella stessa clausola senza che sia necessaria sintassi aggiuntiva.  
  
 Entity SQL impone anche restrizioni aggiuntive per le query che coinvolgono le `group by` clausole. Le espressioni nella `select` clausola e nella `having` clausola di tali query possono fare riferimento solo alle `group by` chiavi tramite i relativi alias. Il costrutto seguente è valido in Transact-SQL, ma non in Entity SQL:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 A tale scopo, Entity SQL:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Riferimento a colonne (proprietà) di tabelle (raccolte)  
 Tutti i riferimenti alle colonne in Entity SQL devono essere qualificati con l'alias di tabella. Il costrutto seguente (presupponendo che `a` sia una colonna valida della tabella `T` ) è valido in Transact-SQL ma non in Entity SQL.  
  
```sql  
SELECT a FROM T
```  
  
 Il modulo Entity SQL è  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Gli alias di tabella sono facoltativi nella clausola `from`. Il nome della tabella viene usato come l'alias implicito. Entity SQL consente anche il formato seguente:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navigazione negli oggetti  
 Transact-SQL utilizza la notazione "." per fare riferimento a colonne di (una riga di) una tabella. Entity SQL estende questa notazione (presa in prestito dai linguaggi di programmazione) per supportare la navigazione tra le proprietà di un oggetto.  
  
 Se, ad esempio, `p` è un'espressione di tipo Person, di seguito viene riportata la sintassi Entity SQL per fare riferimento alla città dell'indirizzo di questa persona.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>Nessun supporto per\*  
 Transact-SQL supporta la sintassi non qualificata \* come alias per l'intera riga e la sintassi qualificata \* (t. \* ) come collegamento per i campi di tale tabella. Transact-SQL consente inoltre di effettuare un'aggregazione Count ( \* ) speciale, che include valori null.  
  
 Entity SQL non supporta il costrutto *. Le query Transact-SQL del form `select * from T` e `select T1.* from T1, T2...` possono essere espresse in Entity SQL `select value t from T as t` rispettivamente come e `select value t1 from T1 as t1, T2 as t2...` . Questi costrutti consentono inoltre di gestire l'ereditarietà (sostituibilità del valore), mentre le varianti `select *` sono limitate alle proprietà di primo livello del tipo dichiarato.  
  
 Entity SQL non supporta l' `count(*)` aggregazione. Usare invece `count(0)`.  
  
## <a name="changes-to-group-by"></a>Modifiche a Group By  
 Entity SQL supporta l'aliasing delle `group by` chiavi. Le espressioni nella clausola `select` e nella clausola `having` devono fare riferimento alle chiavi `group by` attraverso questi alias. Ad esempio, questo Entity SQL sintassi:  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... equivale al seguente Transact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Aggregazioni basate sulle raccolte  
 Entity SQL supporta due tipi di aggregati.  
  
 Le aggregazioni basate sulle raccolte operano sulle raccolte e producono il risultato aggregato. Possono essere presenti in un punto qualsiasi nella query e non richiedono una clausola `group by`. Ad esempio:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 Entity SQL supporta inoltre le aggregazioni di tipo SQL. Ad esempio:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Utilizzo della clausola ORDER BY  
Transact-SQL consente `ORDER BY` di specificare le clausole solo nel blocco in primo piano `SELECT .. FROM .. WHERE` . In Entity SQL, è possibile utilizzare un'espressione annidata che `ORDER BY` può essere inserita in un punto qualsiasi della query, ma l'ordinamento in una query nidificata non viene mantenuto.  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>Identificatori  
 In Transact-SQL il confronto degli identificatori si basa sulle regole di confronto del database corrente. In Entity SQL gli identificatori sono sempre senza distinzione tra maiuscole e minuscole e con distinzione tra caratteri accentati, ovvero Entity SQL distingue tra caratteri accentati e non accentati. ad esempio,' a' non è uguale a' mentre viene operata '. Entity SQL considera le versioni delle lettere che risultano uguali, ma che sono da tabelle codici diverse come caratteri diversi. Per altre informazioni, vedere [set di caratteri di input](input-character-set-entity-sql.md).  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Funzionalità Transact-SQL non disponibili in Entity SQL  
 Le seguenti funzionalità di Transact-SQL non sono disponibili in Entity SQL.  
  
 DML  
 Entity SQL attualmente non fornisce supporto per le istruzioni DML (Insert, Update, Delete).  
  
 DDL  
 Entity SQL non fornisce alcun supporto per DDL nella versione corrente.  
  
 programmazione imperativa  
 Entity SQL non fornisce alcun supporto per la programmazione imperativa, a differenza di Transact-SQL. Usare invece un linguaggio di programmazione.  
  
 Funzioni di raggruppamento  
 Entity SQL non fornisce ancora supporto per le funzioni di raggruppamento, ad esempio CUBE, ROLLUP e GROUPING_SET.  
  
 Funzioni di analisi  
 Entity SQL non è ancora disponibile il supporto per le funzioni analitiche.  
  
 Funzioni e operatori predefiniti  
 Entity SQL supporta un subset di funzioni e operatori predefiniti di Transact-SQL. Questi operatori e funzioni saranno supportati probabilmente dai provider dell'archivio principali. Entity SQL usa le funzioni specifiche dell'archivio dichiarate in un manifesto del provider. Inoltre, il Entity Framework consente di dichiarare le funzioni di archiviazione predefinite e definite dall'utente, che possono essere usate da Entity SQL.  
  
 Hint  
 Entity SQL non fornisce meccanismi per gli hint per la query.  
  
 Invio in batch dei risultati di query  
 Entity SQL non supporta l'invio in batch dei risultati di query. Ad esempio, di seguito è riportato un codice Transact-SQL valido (inviato come batch):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Tuttavia, il Entity SQL equivalente non è supportato:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 Entity SQL supporta solo un'istruzione di query che produce risultati per ogni comando.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su Entity SQL](entity-sql-overview.md)
- [Espressioni non supportate](unsupported-expressions-entity-sql.md)
