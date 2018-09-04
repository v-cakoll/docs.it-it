---
title: Riferimento a Entity SQL
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: ae0aec999d30d099467be690b8920d1413b564f0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515498"
---
# <a name="entity-sql-reference"></a>Riferimento a Entity SQL

In questa sezione contiene gli articoli di riferimento di Entity SQL. Questo articolo sono riepilogati e raggruppati gli operatori di Entity SQL per categoria.

## <a name="arithmetic-operators"></a>Operatori aritmetici

Gli operatori aritmetici eseguono operazioni matematiche su due espressioni di uno o più tipi di dati numerici. Nella tabella seguente sono elencati gli operatori aritmetici Entity SQL:

|Operatore|Usa|
|--------------|---------|
|[+ (addizione)](add.md)|Addizione.|
|[/ (divisione)](divide-entity-sql.md)|Divisione.|
|[% (Modulo)](modulo-entity-sql.md)|Restituisce il resto di una divisione.|
|[* (moltiplicazione)](multiply-entity-sql.md)|Moltiplicazione.|
|[- (negativo)](negative-entity-sql.md)|Negazione.|
|[- (sottrazione)](subtract-entity-sql.md)|Sottrazione.|

## <a name="canonical-functions"></a>Funzioni canoniche

Le funzioni canoniche sono supportate da tutti i provider di dati e possono essere usate da tutte le tecnologie di query. La tabella seguente elenca le funzioni canoniche:

|Funzione|Tipo|
|--------------|----------|
|[Funzioni canoniche di aggregazione di Entity SQL](aggregate-canonical-functions.md)|Vengono illustrate le funzioni canoniche di aggregazione Entity SQL.|
|[Funzioni matematiche canoniche](math-canonical-functions.md)|Descrive funzioni canoniche matematiche Entity SQL.|
|[Funzioni stringa canoniche](string-canonical-functions.md)|Vengono illustrate le funzioni canoniche di stringa Entity SQL.|
|[Funzioni data e ora canoniche](date-and-time-canonical-functions.md)|Vengono illustrate le funzioni canoniche di Entity SQL Data e ora.|
|[Funzioni bit per bit canoniche](bitwise-canonical-functions.md)|Vengono illustrate le funzioni canoniche di Entity SQL bit per bit.|
|[Altre funzioni canoniche](other-canonical-functions.md)|Vengono illustrate le funzioni non classificate come bit per bit, di data e ora, per i valori stringa, matematiche o di aggregazione.|

## <a name="comparison-operators"></a>Operatori di confronto

Gli operatori di confronto sono definiti per i tipi seguenti: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time`, `DateTimeOffset`. La promozione dei tipi impliciti si verifica per gli operandi prima dell'applicazione dell'operatore di confronto. Gli operatori di confronto producono sempre valori booleani. Quando almeno uno degli operandi è `null`, il risultato è `null`.

L'uguaglianza e l'ineguaglianza sono definite per qualsiasi tipo di oggetto con un'identità, ad esempio il tipo `Boolean`. Gli oggetti non primitivi con identità sono considerati uguali se condividono la stessa identità. Nella tabella seguente sono elencati gli operatori di confronto di Entity SQL:

|Operatore|Descrizione|
|--------------|-----------------|
|[= (uguale a)](equals-entity-sql.md)|Consente di confrontare due espressioni per verificare se sono uguali.|
|[> (maggiore di)](greater-than-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.|
|[>= (maggiore di o uguale a)](greater-than-or-equal-to-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.|
|[VIENE \[NON\] NULL](isnull-entity-sql.md)|Consente di determinare se un'espressione di query è null.|
|[< (minore di)](less-than-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore di quella a destra.|
|[<= (minore di o uguale a)](less-than-or-equal-to-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.|
|[\[NON\] BETWEEN](between-entity-sql.md)|Determina se un'espressione restituisce un valore incluso in un intervallo specificato.|
|[\!= (Diverso da)](not-equal-to-entity-sql.md)|Confronta due espressioni per determinare se l'espressione a sinistra non è uguale a quella a destra.|
|[\[NON\] , AD ESEMPIO](like-entity-sql.md)|Determina se una determinata stringa di caratteri corrisponde a un modello specificato.|

## <a name="logical-and-case-expression-operators"></a>Operatori logici e di espressione case

Gli operatori logici verificano la veridicità di una condizione. L'espressione CASE valuta un set di espressioni booleane per determinare il risultato. Nella tabella seguente vengono elencati gli operatori logici e di espressione CASE:

|Operatore|Descrizione|
|--------------|-----------------|
|[& & (AND logico)](and-entity-sql.md)|AND logico.|
|[\! (NOT logico)](not-entity-sql.md)|NOT logico.|
|[&#124;&#124;(OR logico)](or-entity-sql.md)|OR logico.|
|[CASE](case-entity-sql.md)|Valuta un set di espressioni booleane per determinare il risultato.|
|[THEN](then-entity-sql.md)|Il risultato di una [quando](https://msdn.microsoft.com/library/6233fe9f-00b0-460e-8372-64e138a5f998) clausola quando viene valutata come vera.|

## <a name="query-operators"></a>Operatori di query

Gli operatori di query sono usati per definire espressioni di query che restituiscono dati dell'entità. Nella tabella seguente sono elencati gli operatori di query:

|Operatore|Usa|
|--------------|---------|
|[FROM](from-entity-sql.md)|Specifica la raccolta che viene utilizzata [seleziona](select-entity-sql.md) istruzioni.|
|[GROUP BY](group-by-entity-sql.md)|Specifica i gruppi in cui gli oggetti che sono restituiti da una query ([seleziona](select-entity-sql.md)) espressione devono essere inseriti.|
|[GroupPartition](grouppartition-entity-sql.md)|Restituisce una raccolta di valori di argomento, estratta dalla partizione di gruppo alla quale è correlata l'aggregazione.|
|[HAVING](having-entity-sql.md)|Specifica una condizione di ricerca per un gruppo o un'aggregazione.|
|[LIMIT](limit-entity-sql.md)|Utilizzato con il [ORDER BY](order-by-entity-sql.md) clausola per eseguire il paging fisico.|
|[ORDER BY](order-by-entity-sql.md)|Specifica l'ordinamento usato per gli oggetti restituiti un [seleziona](select-entity-sql.md) istruzione.|
|[SELECT](select-entity-sql.md)|Specifica gli elementi nella proiezione che sono restituiti da una query.|
|[SKIP](skip-entity-sql.md)|Utilizzato con il [ORDER BY](order-by-entity-sql.md) clausola per eseguire il paging fisico.|
|[TOP](top-entity-sql.md)|Specifica che verrà restituito solo il primo set di righe del risultato della query.|
|[WHERE](where-entity-sql.md)|Filtra condizionatamente i dati che sono restituiti da una query.|

## <a name="reference-operators"></a>Operatori di riferimento

Un riferimento è un puntatore logico (chiave esterna) a un'entità specifica in un set di entità specifico. Entity SQL supporta gli operatori seguenti per costruire o annullare, nonché navigazione nei riferimenti:

|Operatore|Usa|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Consente di creare riferimenti a un'entità in un set di entità.|
|[DEREF](deref-entity-sql.md)|Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.|
|[KEY](key-entity-sql.md)|Estrae la chiave di un riferimento o di un'espressione di entità.|
|[NAVIGATE](navigate-entity-sql.md)|Consente di eseguire la navigazione da un tipo di entità a un altro|
|[REF](ref-entity-sql.md)|Restituisce un riferimento a un'istanza dell'entità.|

## <a name="set-operators"></a>Operatori Set

Entity SQL sono disponibili diversi importanti operatori sui set. Ciò include operatori set simili agli operatori Transact-SQL quali UNION, INTERSECT, EXCEPT ed EXISTS. Entity SQL supporta anche gli operatori per l'eliminazione dei duplicati (SET), verifica dell'appartenenza (IN) e join (JOIN). Nella tabella seguente sono elencati gli operatori sui set di entità SQL:

|Operatore|Usa|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Estrae un elemento da una raccolta multivalore.|
|[EXCEPT](except-entity-sql.md)|Restituisce una raccolta di tutti i valori distinti dall'espressione di query a sinistra dell'operando EXCEPT che non vengono inoltre restituite dall'espressione di query a destra dell'operando EXCEPT.|
|[\[NON\] EXISTS](exists-entity-sql.md)|Determina se una raccolta è vuota.|
|[FLATTEN](flatten-entity-sql.md)|Converte una raccolta di raccolte in una raccolta bidimensionale.|
|[\[NON\] IN](in-entity-sql.md)|Determina se un valore corrisponde a qualsiasi valore in una raccolta.|
|[INTERSECT](intersect-entity-sql.md)|Restituisce una raccolta di tutti i valori distinti restituiti da entrambe le espressioni di query a sinistra e a destra dell'operando INTERSECT.|
|[OVERLAPS](overlaps-entity-sql.md)|Determina se due raccolte includono elementi comuni.|
|[SET](set-entity-sql.md)|Usato per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.|
|[UNION](union-entity-sql.md)|Combina i risultati di due o più query in una singola raccolta.|

## <a name="type-operators"></a>Operatori di tipo

Entity SQL sono disponibili operazioni che consentono il tipo di un'espressione (valore) viene costruito, eseguire una query e modificate. La tabella seguente elenca gli operatori che consentono di usare i tipi:

|Operatore|Usa|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Consente di convertire un'espressione da un tipo di dati a un altro.|
|[COLLECTION](collection-entity-sql.md)|Utilizzato in una [funzione](function-entity-sql.md) operazione per dichiarare una raccolta di tipi di entità o tipi complessi.|
|[VIENE \[NON\] OF](isof-entity-sql.md)|Determina se il tipo di un'espressione è del tipo specificato o di uno dei sottotipi.|
|[OFTYPE](oftype-entity-sql.md)|Restituisce una raccolta di oggetti da un'espressione di query appartenente a un tipo specifico.|
|[Costruttore di tipo denominato](named-type-constructor-entity-sql.md)|Usato per creare istanze di tipi di entità o tipi complessi.|
|[MULTISET](multiset-entity-sql.md)|Crea un'istanza di un multiset da un elenco di valori.|
|[ROW](row-entity-sql.md)|Consente di costruire record anonimi strutturalmente tipizzati da uno o più valori.|
|[TREAT](treat-entity-sql.md)|Consente di trattare un oggetto di un tipo di base particolare come oggetto del tipo derivato specificato.|

## <a name="other-operators"></a>Altri operatori

Nella tabella seguente sono elencati altri operatori di Entity SQL:

|Operatore|Usa|
|--------------|---------|
|[+ (concatenazione di stringhe)](string-concatenation-entity-sql.md)|Usato per concatenare le stringhe in Entity SQL.|
|[. (Accesso ai membri)](member-access-entity-sql.md)|Usato per accedere al valore di una proprietà o di un campo di un'istanza di tipo di modello concettuale strutturale.|
|[-- (commento)](comment-entity-sql.md)|Includere commenti Entity SQL.|
|[FUNCTION](function-entity-sql.md)|Definisce una funzione inline che può essere eseguita in una query Entity SQL.|

## <a name="see-also"></a>Vedere anche

[Linguaggio Entity SQL](entity-sql-language.md)
