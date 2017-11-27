---
title: Riferimento a Entity SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 776a2a93f559ba54651adc49e6b609c8156e9e31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="entity-sql-reference"></a>Riferimento a Entity SQL
In questa sezione sono contenuti gli argomenti di riferimento a [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. In questo argomento sono riepilogati e raggruppati i [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori per categoria.  
  
## <a name="arithmetic-operators"></a>Operatori aritmetici  
 Gli operatori aritmetici eseguono operazioni matematiche su due espressioni di uno o più tipi di dati numerici. Nella tabella seguente sono inclusi gli operatori aritmetici di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Operatore|Usa|  
|--------------|---------|  
|[+ (Addizione)](../../../../../../docs/framework/data/adonet/ef/language-reference/add.md)|Addizione.|  
|"/ (Divisione)"|Divisione.|  
|[% (Modulo)](../../../../../../docs/framework/data/adonet/ef/language-reference/modulo-entity-sql.md)|Restituisce il resto di una divisione.|  
|[* (Moltiplicazione)](../../../../../../docs/framework/data/adonet/ef/language-reference/multiply-entity-sql.md)|Moltiplicazione.|  
|[-(Negativo)](../../../../../../docs/framework/data/adonet/ef/language-reference/negative-entity-sql.md)|Negazione.|  
|[-(Sottrazione)](../../../../../../docs/framework/data/adonet/ef/language-reference/subtract-entity-sql.md)|Sottrazione.|  
  
## <a name="canonical-functions"></a>Funzioni canoniche  
 Le funzioni canoniche sono supportate da tutti i provider di dati e possono essere usate da tutte le tecnologie di query. Nella tabella seguente sono elencate le funzioni canoniche.  
  
|Funzione|Tipo|  
|--------------|----------|  
|[Funzioni canoniche di aggregazione di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] di aggregazione.|  
|[Funzioni matematiche canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] matematiche.|  
|[Funzioni stringa canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per i valori stringa.|  
|[Funzioni data e ora canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] di data e ora.|  
|[Bit per bit funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Vengono illustrate le funzioni canoniche [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bit per bit.|  
|[Altre funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)|Vengono illustrate le funzioni non classificate come bit per bit, di data e ora, per i valori stringa, matematiche o di aggregazione.|  
  
## <a name="comparison-operators"></a>Operatori di confronto  
 Gli operatori di confronto sono definiti per i tipi seguenti: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time`, `DateTimeOffset`. La promozione dei tipi impliciti si verifica per gli operandi prima dell'applicazione dell'operatore di confronto. Gli operatori di confronto producono sempre valori booleani. Quando almeno uno degli operandi è `null`, il risultato è `null`.  
  
 L'uguaglianza e l'ineguaglianza sono definite per qualsiasi tipo di oggetto con un'identità, ad esempio il tipo `Boolean`. Gli oggetti non primitivi con identità sono considerati uguali se condividono la stessa identità. Nella tabella seguente vengono elencati gli operatori di confronto [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Operatore|Descrizione|  
|--------------|-----------------|  
|[= (Uguale a)](../../../../../../docs/framework/data/adonet/ef/language-reference/equals-entity-sql.md)|Consente di confrontare due espressioni per verificare se sono uguali.|  
|[> (Maggiore di)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.|  
|[> = (maggiore o uguale a)](../../../../../../docs/framework/data/adonet/ef/language-reference/greater-than-or-equal-to-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.|  
|[È &#91; NON &#93; NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/isnull-entity-sql.md)|Consente di determinare se un'espressione di query è null.|  
|[< (Minore di)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore di quella a destra.|  
|[< = (minore o uguale a)](../../../../../../docs/framework/data/adonet/ef/language-reference/less-than-or-equal-to-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.|  
|[&#91; NON &#93; TRA](../../../../../../docs/framework/data/adonet/ef/language-reference/between-entity-sql.md)|Determina se un'espressione restituisce un valore incluso in un intervallo specificato.|  
|[! = (Diverso da)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-equal-to-entity-sql.md)|Consente di confrontare due espressioni per determinare se l'espressione a sinistra è diversa da quella a destra.|  
|[&#91; NON &#93; AD ESEMPIO](../../../../../../docs/framework/data/adonet/ef/language-reference/like-entity-sql.md)|Determina se una determinata stringa di caratteri corrisponde a un modello specificato.|  
  
## <a name="logical-and-case-expression-operators"></a>Operatori logici e di espressione Case  
 Gli operatori logici verificano la veridicità di una condizione. L'espressione CASE valuta un set di espressioni booleane per determinare il risultato. Nella tabella seguente sono inclusi gli operatori logici e di espressione CASE.  
  
|Operatore|Descrizione|  
|--------------|-----------------|  
|[& & (AND logico)](../../../../../../docs/framework/data/adonet/ef/language-reference/and-entity-sql.md)|AND logico.|  
|[! (NOT logico)](../../../../../../docs/framework/data/adonet/ef/language-reference/not-entity-sql.md)|NOT logico.|  
|[&#124; &#124; (OR logico)](../../../../../../docs/framework/data/adonet/ef/language-reference/or-entity-sql.md)|OR logico.|  
|[CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)|Valuta un set di espressioni booleane per determinare il risultato.|  
|[QUINDI](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)|Il risultato di un [quando](http://msdn.microsoft.com/en-us/6233fe9f-00b0-460e-8372-64e138a5f998) clausola quando restituisce true.|  
  
## <a name="query-operators"></a>Operatori di query  
 Gli operatori di query sono usati per definire espressioni di query che restituiscono dati dell'entità. Nella tabella seguente sono elencati gli operatori di query.  
  
|Operatore|Usa|  
|--------------|---------|  
|[DA](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md)|Specifica la raccolta che viene utilizzata in [selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) istruzioni.|  
|[RAGGRUPPA PER](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)|Specifica i gruppi in cui gli oggetti che vengono restituiti da una query ([selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) espressione devono essere inseriti.|  
|[GroupPartition](../../../../../../docs/framework/data/adonet/ef/language-reference/grouppartition-entity-sql.md)|Restituisce una raccolta di valori di argomento, estratta dalla partizione di gruppo alla quale è correlata l'aggregazione.|  
|[CON](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)|Specifica una condizione di ricerca per un gruppo o un'aggregazione.|  
|[LIMITE](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)|Utilizzato con il [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola per eseguire il paging fisico.|  
|[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)|Specifica l'ordinamento utilizzato per gli oggetti restituiti un [selezionare](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) istruzione.|  
|[SELEZIONARE](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)|Specifica gli elementi nella proiezione che sono restituiti da una query.|  
|[SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)|Utilizzato con il [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) clausola per eseguire il paging fisico.|  
|[IN ALTO](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)|Specifica che verrà restituito solo il primo set di righe del risultato della query.|  
|[DOVE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)|Filtra condizionatamente i dati che sono restituiti da una query.|  
  
## <a name="reference-operators"></a>Operatori di riferimento  
 Un riferimento è un puntatore logico (chiave esterna) a un'entità specifica in un set di entità specifico. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]supporta gli operatori seguenti per costruire o annullare, nonché esplorare i riferimenti.  
  
|Operatore|Usa|  
|--------------|---------|  
|[CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)|Consente di creare riferimenti a un'entità in un set di entità.|  
|[DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)|Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.|  
|[CHIAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)|Estrae la chiave di un riferimento o di un'espressione di entità.|  
|[PASSARE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)|Consente di eseguire la navigazione da un tipo di entità a un altro|  
|[REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)|Restituisce un riferimento a un'istanza dell'entità.|  
  
## <a name="set-operators"></a>Operatori Set  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono disponibili diversi importanti operatori sui set, Ciò include operatori set simili agli operatori Transact-SQL quali UNION, INTERSECT, EXCEPT ed EXISTS. In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sono inoltre supportati operatori per l'eliminazione dei duplicati (SET), la verifica dell'appartenenza (IN) e i join (JOIN). Nella tabella seguente sono elencati gli operatori Set [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Operatore|Usa|  
|--------------|---------|  
|[ANYELEMENT](../../../../../../docs/framework/data/adonet/ef/language-reference/anyelement-entity-sql.md)|Estrae un elemento da una raccolta multivalore.|  
|[LA DIFFERENZA](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)|Restituisce una raccolta di tutti i valori distinti dell'espressione di query a sinistra dell'operando EXCEPT che non vengono restituiti anche dall'espressione di query a destra dell'operando EXCEPT.|  
|[&#91; NON &#93; ESISTE](../../../../../../docs/framework/data/adonet/ef/language-reference/exists-entity-sql.md)|Determina se una raccolta è vuota.|  
|[RENDERE BIDIMENSIONALE](../../../../../../docs/framework/data/adonet/ef/language-reference/flatten-entity-sql.md)|Converte una raccolta di raccolte in una raccolta bidimensionale.|  
|[&#91; NON &#93; IN](../../../../../../docs/framework/data/adonet/ef/language-reference/in-entity-sql.md)|Determina se un valore corrisponde a qualsiasi valore in una raccolta.|  
|[SI INTERSECANO](../../../../../../docs/framework/data/adonet/ef/language-reference/intersect-entity-sql.md)|Restituisce una raccolta di tutti i valori distinti restituiti da entrambe le espressioni di query a sinistra e a destra dell'operando INTERSECT.|  
|[SI SOVRAPPONE](../../../../../../docs/framework/data/adonet/ef/language-reference/overlaps-entity-sql.md)|Determina se due raccolte includono elementi comuni.|  
|[SET](../../../../../../docs/framework/data/adonet/ef/language-reference/set-entity-sql.md)|Usato per convertire una raccolta di oggetti in un set restituendo una nuova raccolta da cui sono stati rimossi tutti i duplicati.|  
|[UNION](../../../../../../docs/framework/data/adonet/ef/language-reference/union-entity-sql.md)|Combina i risultati di due o più query in una singola raccolta.|  
  
## <a name="type-operators"></a>Operatori di tipo  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]fornisce le operazioni che consentono il tipo di un'espressione (valore) viene costruito, eseguire una query e modificato. Nella tabella seguente sono elencati gli operatori usati per lavorare con i tipi.  
  
|Operatore|Usa|  
|--------------|---------|  
|[CAST](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)|Consente di convertire un'espressione da un tipo di dati a un altro.|  
|[RACCOLTA](../../../../../../docs/framework/data/adonet/ef/language-reference/collection-entity-sql.md)|Utilizzato un [funzione](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operazione per dichiarare una raccolta di tipi di entità o tipi complessi.|  
|[È &#91; NON &#93; DI](../../../../../../docs/framework/data/adonet/ef/language-reference/isof-entity-sql.md)|Determina se il tipo di un'espressione è del tipo specificato o di uno dei sottotipi.|  
|[OFTYPE](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)|Restituisce una raccolta di oggetti da un'espressione di query appartenente a un tipo specifico.|  
|[Costruttore di tipo denominato](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)|Usato per creare istanze di tipi di entità o tipi complessi.|  
|[MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)|Crea un'istanza di un multiset da un elenco di valori.|  
|[RIGA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)|Consente di costruire record anonimi strutturalmente tipizzati da uno o più valori.|  
|[TREAT](../../../../../../docs/framework/data/adonet/ef/language-reference/treat-entity-sql.md)|Consente di trattare un oggetto di un tipo di base particolare come oggetto del tipo derivato specificato.|  
  
## <a name="other-operators"></a>Altri operatori  
 Nella tabella seguente sono elencati altri [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori.  
  
|Operatore|Usa|  
|--------------|---------|  
|[+ (Concatenazione di stringhe)](../../../../../../docs/framework/data/adonet/ef/language-reference/string-concatenation-entity-sql.md)|Usato per concatenare stringhe in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[. (Accesso ai membri)](../../../../../../docs/framework/data/adonet/ef/language-reference/member-access-entity-sql.md)|Usato per accedere al valore di una proprietà o di un campo di un'istanza di tipo di modello concettuale strutturale.|  
|[-(Commento)](../../../../../../docs/framework/data/adonet/ef/language-reference/comment-entity-sql.md)|Include commenti [!INCLUDE[esql](../../../../../../includes/esql-md.md)].|  
|[(FUNZIONE)](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md)|Definisce una funzione inline che può essere eseguita in una query Entity SQL.|  
  
## <a name="see-also"></a>Vedere anche  
 [Linguaggio Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
