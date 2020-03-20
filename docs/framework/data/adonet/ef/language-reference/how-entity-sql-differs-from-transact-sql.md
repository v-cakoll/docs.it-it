---
title: Differenze tra Entity SQL e Transact-SQL
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150231"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Differenze tra Entity SQL e Transact-SQL
In questo argomento vengono [!INCLUDE[esql](../../../../../../includes/esql-md.md)] descritte le differenze tra e Transact-SQLTransact-SQL.  
  
## <a name="inheritance-and-relationships-support"></a>Supporto di ereditarietà e relazioni  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]funziona direttamente con schemi di entità concettuali e supporta le funzionalità del modello concettuale, ad esempio l'ereditarietà e le relazioni.  
  
 Quando si usa l'ereditarietà, è spesso utile selezionare le istanze di un sottotipo da una raccolta di istanze di supertipi. L'operatore [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [oftype](oftype-entity-sql.md) `oftype` in (simile a nelle sequenze C ) fornisce questa funzionalità.  
  
## <a name="support-for-collections"></a>Supporto per le raccolte  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]considera le raccolte come entità di prima classe. Ad esempio:  
  
- Le espressioni della Collection sono valide in una clausola `from`.  
  
- Le sottoquery `in` e `exists` sono state generalizzate per consentire qualsiasi raccolta.  
  
     Una sottoquery è un tipo di raccolta. `e1 in e2` e `exists(e)` sono i construct [!INCLUDE[esql](../../../../../../includes/esql-md.md)] usati per eseguire queste operazioni.  
  
- Le operazioni Set, ad esempio `union`, `intersect` ed `except`, possono ora essere usate sulle raccolte.  
  
- I join funzionano sulle raccolte.  
  
## <a name="support-for-expressions"></a>Supporto per le espressioni  
 Transact-SQLTransact-SQL include sottoquery (tabelle) ed espressioni (righe e colonne).  
  
 Per supportare raccolte [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e raccolte annidate, rende tutto un'espressione. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]è più componibile di Transact-SQLTransact-SQL: ogni espressione può essere utilizzata ovunque. Le espressioni di query restituiscono sempre raccolte dei tipi previsti e possono essere usate in qualunque posizione in cui è consentita un'espressione sulle raccolte. Per informazioni sulle espressioni Transact-SQLTransact-SQL non supportate in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere Espressioni non [supportate](unsupported-expressions-entity-sql.md).  
  
 Le query seguenti sono tutte query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] valide:  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>Modalità di gestione uniforme delle sottoquery  
 Data l'enfasi sulle tabelle, Transact-SQLTransact-SQL esegue un'interpretazione contestuale delle sottoquery. Ad esempio, una sottoquery nella `from` clausola viene considerata un multiset (tabella). La stessa sottoquery usata nella clausola `select` viene invece considerata come una sottoquery scalare. Analogamente, una sottoquery utilizzata sul `in` lato sinistro di un operatore è considerata una sottoquery scalare, mentre il lato destro dovrebbe essere una sottoquery multiset.  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono eliminate queste differenze. Un'espressione dispone di un'interpretazione uniforme che non dipende dal contesto in cui viene usata. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]considera tutte le sottoquery come sottoquery multiset. Se si desidera un valore scalare [!INCLUDE[esql](../../../../../../includes/esql-md.md)] dalla `anyelement` sottoquery, fornisce l'operatore che opera su una raccolta (in questo caso, la sottoquery) ed estrae un valore singleton dalla raccolta.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>Eliminazione della presenza di coercizioni implicite per le sottoquery  
 Un effetto collaterale della modalità di gestione uniforme delle sottoquery è la conversione implicita delle sottoquery in valori scalari. In particolare, in Transact-SQLTransact-SQL, un multiset di righe (con un singolo campo) viene convertito in modo implicito in un valore scalare il cui tipo di dati è quello del campo.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non supporta questa coercizione implicita. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce un operatore ANYELEMENT per estrarre un valore Singleton da una raccolta e una clausola `select value` per evitare di creare un wrapper di riga durante un'espressione di query.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>SELECT VALUE: eliminazione della presenza del wrapper di riga implicito  
 La clausola select in una sottoquery Transact-SQL crea in modo implicito un wrapper di riga intorno agli elementi nella clausola. Questo implica che non si possono creare raccolte di scalari o oggetti. Transact-SQLTransact-SQL consente una coercizione implicita tra un tipo di riga con un campo e un valore singleton dello stesso tipo di dati.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce la clausola `select value` per ignorare la costruzione di riga implicita. Nella clausola `select value` è possibile specificare un solo elemento. Quando viene usata questa clausola, non viene costruito alcun wrapper di riga intorno agli elementi nella clausola `select` e può essere prodotta una raccolta della forma desiderata, ad esempio `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce inoltre il costruttore ROW per la costruzione di righe arbitrarie. `select` prende uno o più elementi nella proiezione e crea un record di dati con campi, come mostrato di seguito:  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>Correlazione sinistra e utilizzo di alias  
 In Transact-SQLTransact-SQL le espressioni in `select` un `from`determinato ambito (una singola clausola come or ) non possono fare riferimento a espressioni definite in precedenza nello stesso ambito. Alcuni dialetti di SQL (incluso Transact-SQLTransact-SQL) `from` supportano forme limitate di questi nella clausola.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]generalizza le correlazioni `from` lasciate nella clausola e le tratta in modo uniforme. Le espressioni nella clausola `from` possono fare riferimento a definizioni precedenti (definizioni a sinistra) nella stessa clausola senza che sia necessaria sintassi aggiuntiva.  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono inoltre imposte restrizioni aggiuntive sulle query che implicano l'uso di clausole `group by`. Le espressioni `select` nella `having` clausola e nella clausola di tali query possono fare riferimento alle `group by` chiavi solo tramite i relativi alias. Il costrutto seguente è valido in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]Transact-SQLTransact-SQL ma non è in:  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 Per eseguire questa operazione in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>Riferimento a colonne (proprietà) di tabelle (raccolte)  
 Tutti i riferimenti alle colonne in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] devono essere qualificati con l'alias di tabella. Il costrutto seguente `a` (presupponendo che `T`sia una colonna valida della [!INCLUDE[esql](../../../../../../includes/esql-md.md)]tabella ) è valido in Transact-SQLTransact-SQL ma non in .  
  
```sql  
SELECT a FROM T
```  
  
 Il formato in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è:  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 Gli alias di tabella sono facoltativi nella clausola `from`. Il nome della tabella viene usato come l'alias implicito. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consente anche l'uso del formato seguente:  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>Navigazione negli oggetti  
 Transact-SQLTransact-SQL usa la notazione "." per fare riferimento a colonne di (una riga di) una tabella. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] estende questa notazione (preso in prestito dai linguaggi di programmazione) per supportare la navigazione tra le proprietà di un oggetto.  
  
 Se, ad esempio, `p` è un'espressione del tipo Person, di seguito è riportata la sintassi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] che consente di fare riferimento alla città dell'indirizzo di tale persona.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>Mancanza di supporto per *  
 Transact-SQLTransact-SQL supporta la sintassi non qualificata, ovvero \* come alias\*per l'intera riga, e la sintassi qualificata (t. ) come collegamento per i campi di tale tabella. Inoltre, Transact-SQLTransact-SQL consente\*un'aggregazione count( ) speciale, che include valori Null.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non supporta il construct *. Le query Transact-SQLTransact-SQL nel [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `select value t from T as t` modulo `select value t1 from T1 as t1, T2 as t2...` `select * from T` e `select T1.* from T1, T2...` possono essere espresse rispettivamente come e , . Questi costrutti consentono inoltre di gestire l'ereditarietà (sostituibilità del valore), mentre le varianti `select *` sono limitate alle proprietà di primo livello del tipo dichiarato.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non supporta l'aggregato `count(*)`. Usare invece `count(0)`.  
  
## <a name="changes-to-group-by"></a>Modifiche a Group By  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta l'uso di alias delle chiavi `group by`. Le espressioni nella clausola `select` e nella clausola `having` devono fare riferimento alle chiavi `group by` attraverso questi alias. La sintassi [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente:  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... è equivalente ai seguenti Transact-SQLTransact-SQL:  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>Aggregazioni basate sulle raccolte  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta due tipi di aggregazioni.  
  
 Le aggregazioni basate sulle raccolte operano sulle raccolte e producono il risultato aggregato. Possono essere presenti in un punto qualsiasi nella query e non richiedono una clausola `group by`. Ad esempio:  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta inoltre le aggregazioni di tipo SQL. Ad esempio:  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>Utilizzo della clausola ORDER BY  
Transact-SQLTransact-SQL consente `ORDER BY` di specificare `SELECT .. FROM .. WHERE` le clausole solo nel blocco più in alto. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è possibile `ORDER BY` utilizzare un'espressione nidificata che può essere inserita in qualsiasi punto della query, ma l'ordinamento in una query nidificata non viene mantenuto.  
  
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
 In Transact-SQLTransact-SQL il confronto degli identificatori si basa sulle regole di confronto del database corrente. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], gli identificatori non applicano mai la distinzione tra maiuscole e minuscole, mentre applicano la distinzione tra caratteri accentati e non accentati. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] viene infatti applicata la distinzione tra caratteri accentati e non accentati, ad esempio 'a' è diverso da 'à'. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] le versioni delle lettere che hanno lo stesso aspetto ma che provengono da tabelle codici diverse vengono gestite come caratteri differenti. Per ulteriori informazioni, consultate [Set di caratteri di input.](input-character-set-entity-sql.md)  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Funzionalità Transact-SQL non disponibili in Entity SQL  
 La seguente funzionalità Transact-SQLTransact-SQL non è disponibile in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]attualmente non fornisce alcun supporto per le istruzioni DML (inserimento, aggiornamento, eliminazione).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non fornisce supporto per DDL nella versione corrente.  
  
 programmazione imperativa  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]non fornisce alcun supporto per la programmazione imperativa, a differenza di Transact-SQLTransact-SQL. Usare invece un linguaggio di programmazione.  
  
 Funzioni di raggruppamento  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non fornisce ancora supporto per le funzioni di raggruppamento (ad esempio CUBE, ROLLUP e GROUPING_SET).  
  
 Funzioni di analisi  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non fornisce (ancora) supporto per le funzioni analitiche.  
  
 Funzioni e operatori predefiniti  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]supporta un sottoinsieme di funzioni e operatori incorporati di Transact-SQLTransact-SQL. Questi operatori e funzioni saranno supportati probabilmente dai provider dell'archivio principali. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]utilizza le funzioni specifiche dell'archivio dichiarate in un manifesto del provider. Inoltre, Entity Framework consente di dichiarare funzioni di archiviazione esistenti predefinite [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e definite dall'utente, da utilizzare.  
  
 Hint  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non fornisce meccanismi per gli hint per le query.  
  
 Invio in batch dei risultati di query  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non supporta l'invio in batch dei risultati di query. Ad esempio, il seguente è Transact-SQLTransact-SQL valido (invio come batch):  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 Tuttavia, l'espressione equivalente [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è supportata:  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supporta solo un'istruzione di query che restituisce un risultato per comando.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su Entity SQL](entity-sql-overview.md)
- [Espressioni non supportate](unsupported-expressions-entity-sql.md)
