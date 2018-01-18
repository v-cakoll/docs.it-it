---
title: Raccolte di schemi Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4f199a0fc0939bd5fae4fefb7440c46bd471e4b6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-schema-collections"></a>Raccolte di schemi Oracle
Il provider di dati Microsoft .NET Framework per Oracle, oltre alle raccolte di schemi comuni, supporta le seguenti raccolte di schemi specifici:  
  
-   Colonne  
  
-   Indexes  
  
-   IndexColumns  
  
-   Procedure  
  
-   Sequenze  
  
-   Synonyms  
  
-   Tabelle  
  
-   Utenti  
  
-   Visualizzazioni  
  
-   Funzioni  
  
-   Pacchetti  
  
-   PackageBodies  
  
-   Argomenti  
  
-   UniqueKeys  
  
-   PrimaryKeys  
  
-   ForeignKeys  
  
-   ForeignKeyColumns  
  
-   ProcedureParameters  
  
## <a name="columns"></a>Colonne  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della tabella, della visualizzazione o del cluster.|  
|TABLE_NAME|String|Nome della tabella, della visualizzazione o del cluster.|  
|COLUMN_NAME|String|Nome della colonna.|  
|ID|Decimal|Numero di sequenza della colonna in base all'ordine in cui vengono create le colonne.|  
|DATATYPE|String|Tipo di dati della colonna.|  
|LENGTH|Decimal|Lunghezza della colonna in byte.|  
|PRECISION|Decimal|Precisione decimale per il tipo di dati NUMBER e precisione binaria per il tipo di dati FLOAT. Per tutti gli altri tipi di dati, il valore è null.|  
|SCALE|Decimal|Cifre a destra del separatore decimale in un numero.|  
|NULLABLE|String|Specifica se una colonna supporta i valori NULL. Il valore è N se è presente un vincolo diverso da NULL sulla colonna o se la colonna fa parte di un vincolo PRIMARY KEY.|  
  
## <a name="indexes"></a>Indexes  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'indice.|  
|INDEX_NAME|String|Nome dell'indice.|  
|INDEX_TYPE|String|Tipo di indice (NORMAL, BITMAP, FUNCTION-BASED NORMAL, FUNCTION-BASED BITMAP o DOMAIN).|  
|TABLE_OWNER|String|Proprietario dell'oggetto indicizzato.|  
|TABLE_NAME|String|Nome dell'oggetto indicizzato.|  
|TABLE_TYPE|String|Tipo di oggetto indicizzato, ad esempio TABLE e CLUSTER.|  
|UNIQUENESS|String|Se l'indice è UNIQUE o NONUNIQUE.|  
|COMPRESSION|String|Se l'indice è ENABLED o DISABLED.|  
|PREFIX_LENGTH|Decimal|Il numero di colonne nel prefisso della chiave compression.|  
|TABLESPACE_NAME|String|Il nome dello spazio di tabella contenente l'indice.|  
|INI_TRANS|Decimal|Il numero iniziale di transazioni.|  
|MAX_TRANS|Decimal|Il numero massimo di transazioni.|  
|INITIAL_EXTENT|Decimal|La dimensione dell'extent iniziale.|  
|NEXT_EXTENT|Decimal|Dimensione degli extent successivi.|  
|MIN_EXTENTS|Decimal|Numero minimo di extent consentito nel segmento.|  
|MAX_EXTENTS|Decimal|Il numero massimo di extent consentito nel segmento.|  
|PCT_INCREASE|Decimal|La percentuale di aumento della dimensione degli extent.|  
|PCT_THRESHOLD|Decimal|La soglia percentuale di spazio dei blocchi consentita in base alla voce dell'indice.|  
|INCLUDE_COLUMN|Decimal|L'identificatore colonna dell'ultima colonna da includere nell'indice (non overflow) della chiave primaria della tabella con indice. Il mapping di questa colonna viene eseguito alla colonna COLUMN_ID delle visualizzazioni del dizionario dei dati *_TAB_COLUMNS.|  
|FREELISTS|Decimal|Il numero di elenchi di disponibilità di processi allocato al segmento.|  
|FREELIST_GROUPS|Decimal|Il numero di elenchi di disponibilità di gruppi allocato al segmento.|  
|PCT_FREE|Decimal|Percentuale minima di spazio disponibile in un blocco.|  
|LOGGING|String|Le informazioni sulla registrazione.|  
|BLEVEL|Decimal|Livello dell'albero B*: profondità dell'indice dal blocco radice ai relativi blocchi foglia. La profondità 0 indica che il blocco radice e il blocco foglia sono identici.|  
|LEAF_BLOCKS|Decimal|Il numero di blocchi foglia nell'indice.|  
|DISTINCT_KEYS|Decimal|Il numero di valori indicizzati distinti. Per gli indici che impongono i vincoli UNIQUE e PRIMARY KEY, questo valore corrisponde al numero di righe nella tabella (USER_TABLES.NUM_ROWS).|  
|AVG_LEAF_BLOCKS_PER_KEY|Decimal|Il numero medio dei blocchi foglia in cui ciascun valore distinct dell'indice viene arrotondato al valore integer più vicino. Per gli indici che impongono i vincoli UNIQUE e PRIMARY KEY, questo valore è sempre 1.|  
|AVG_DATA_BLOCKS_PER_KEY|Decimal|Il numero medio dei blocchi di dati nella tabella a cui fa riferimento un valore distinct dell'indice arrotondato al valore integer più vicino. Questa statistica rappresenta il numero medio dei blocchi di dati contenenti righe in cui è presente un valore specificato per le colonne indicizzate.|  
|CLUSTERING_FACTOR|Decimal|Indica il livello di ordine delle righe nella tabella in base ai valori dell'indice.|  
|STATO|String|Indica se un indice non partizionato è VALID o UNUSABLE.|  
|NUM_ROWS|Decimal|Il numero di righe dell'indice.|  
|SAMPLE_SIZE|Decimal|Dimensione dell'esempio usato per analizzare l'indice.|  
|LAST_ANALYZED|DateTime|La data più recente in cui è stato analizzato l'indice.|  
|DEGREE|String|Il numero di thread per ogni istanza per l'analisi dell'indice.|  
|INSTANCES|String|Il numero di istanze in cui analizzare gli indici.|  
|PARTITIONED|Stringa|Se l'indice è partizionato (Sì &#124; NO).|  
|TEMPORARY|String|Indica se l'indice è in una tabella temporanea.|  
|GENERATED|Stringa|Se il nome dell'indice è generato dal sistema (Y &#124; N).|  
|SECONDARY|Stringa|Se l'indice è un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|  
|BUFFER_POOL|String|Il nome del pool di buffer predefinito da usare per il blocchi dell'indice.|  
|USER_STATS|String|Indica se le statistiche sono state immesse direttamente dall'utente.|  
|DURATION|String|Indica la durata di una tabella temporanea. 1) SYS$SESSION: le righe vengono mantenute per la durata della sessione. 2) SYS$TRANSACTION: le righe vengono eliminate dopo COMMIT. 3) Null per una tabella permanente.|  
|PCT_DIRECT_ACCESS|Decimal|Indica la percentuale di righe con guess uguale a VALID per un indice secondario in una tabella con indice.|  
|ITYP_OWNER|String|Indica il proprietario del tipo di indice per un indice di dominio.|  
|ITYP_NAME|String|Indica il nome del tipo di indice per un indice di dominio.|  
|PARAMETERS|String|Indica la stringa del parametro per un indice di dominio.|  
|GLOBAL_STATS|String|Per gli indici partizionati, indica se le statistiche sono state raccolte analizzando l'intero indice (YES) o se sono state valutate in base alle statistiche sulle partizioni e sottopartizioni dell'indice sottostanti (NO).|  
|DOMIDX_STATUS|String|Riflette lo stato dell'indice di dominio. NULL: l'indice specificato non è un indice di dominio. VALID: l'indice è un indice di dominio valido. IDXTYP_INVLD: il tipo di indice dell'indice di dominio non è valido.|  
|DOMIDX_OPSTATUS|String|Riflette lo stato di un'operazione eseguita su un indice di dominio. NULL: l'indice specificato non è un indice di dominio. VALID: l'operazione è stata eseguita senza errori. FAILED: si è verificato un errore e l'operazione non è stata eseguita correttamente.|  
|FUNCIDX_STATUS|String|Indica lo stato di un indice basato sulla funzione. NULL: non si tratta di un indice basato sulla funzione. ENABLED: l'indice basato sulla funzione è abilitato. DISABLED: l'indice basato sulla funzione è disabilitato.|  
|JOIN_INDEX|String|Indica se l'indice è un indice di join o meno.|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|INDEX_OWNER|String|Proprietario dell'indice.|  
|INDEX_NAME|String|Nome dell'indice.|  
|TABLE_OWNER|String|Proprietario della tabella o del cluster.|  
|TABLE_NAME|String|Nome della tabella o del cluster.|  
|COLUMN_NAME|String|Nome della colonna o attributo della colonna del tipo oggetto.|  
|COLUMN_POSITION|Decimal|La posizione della colonna o dell'attributo all'interno dell'indice.|  
|COLUMN_LENGTH|Decimal|La lunghezza indicizzata della colonna.|  
|CHAR_LENGTH|Decimal|La lunghezza massima dei punti di codice della colonna.|  
|DESCEND|String|Indica se la colonna è ordinata in ordine decrescente.|  
  
## <a name="procedures"></a>Procedure  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'oggetto.|  
|OBJECT_NAME|String|Nome dell'oggetto.|  
|SUBOBJECT_NAME|String|Nome del sottoggetto, ad esempio una partizione.|  
|OBJECT_ID|Decimal|Il numero dell'oggetto dizionario dell'oggetto.|  
|DATA_OBJECT_ID|Decimal|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|  
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|  
|TIMESTAMP|String|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|  
|STATO|String|Lo stato dell'oggetto (VALID, INVALID o N/A).|  
|TEMPORARY|String|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|  
|GENERATED|String|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|  
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|  
|CREATED|DateTime|Data di creazione dell'oggetto.|  
  
## <a name="sequences"></a>Sequenze  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|SEQUENCE_OWNER|String|Nome del proprietario della sequenza.|  
|SEQUENCE_NAME|String|Il nome della sequenza.|  
|MIN_VALUE|Decimal|Valore minimo della sequenza.|  
|MAX_VALUE|Decimal|Valore massimo della sequenza.|  
|INCREMENT_BY|Decimal|Il valore dell'incremento della sequenza.|  
|CYCLE_FLAG|String|Indica se la sequenza è prossima al raggiungimento del limite.|  
|ORDER_FLAG|String|Indica se i numeri di sequenza sono generati in ordine.|  
|CACHE_SIZE|Decimal|Il numero dei numeri di sequenza da memorizzare nella cache.|  
|LAST_NUMBER|Decimal|L'ultimo numero di sequenza scritto sul disco. Se per una sequenza viene usata la memorizzazione nella cache, il numero scritto sul disco corrisponde all'ultimo numero inserito nella cache delle sequenze. È probabile che questo numero sia maggiore dell'ultimo numero di sequenza usato.|  
  
## <a name="synonyms"></a>Synonyms  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario del sinonimo.|  
|SYNONYM_NAME|String|Nome del sinonimo.|  
|TABLE_OWNER|String|Proprietario dell'oggetto a cui fa riferimento il sinonimo.|  
|TABLE_NAME|String|Il nome dell'oggetto a cui fa riferimento il sinonimo.|  
|DB_LINK|String|Nome del collegamento al database a cui viene fatto riferimento, se presente.|  
  
## <a name="tables"></a>Tabelle  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della tabella.|  
|TABLE_NAME|String|Nome della tabella.|  
|TYPE|String|Tipo di tabella.|  
  
## <a name="users"></a>Utenti  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|NAME|String|Nome dell'utente.|  
|ID|Decimal|Numero ID dell'utente.|  
|CREATEDATE|DateTime|Data di creazione dell'utente.|  
  
## <a name="views"></a>Visualizzazioni  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della visualizzazione.|  
|VIEW_NAME|String|Nome della visualizzazione.|  
|TEXT_LENGTH|Decimal|Lunghezza del testo della visualizzazione.|  
|TEXT|String|Testo della visualizzazione.|  
|TYPE_TEXT_LENGTH|Decimal|Lunghezza della clausola di tipo della visualizzazione tipizzata.|  
|TYPE_TEXT|String|La clausola di tipo della visualizzazione tipizzata.|  
|OID_TEXT_LENGTH|Decimal|La lunghezza della clausola con l'identificatore di oggetto (OID, Object IDentifier) della visualizzazione tipizzata.|  
|OID_TEXT|String|La clausola con l'identificatore di oggetto (OID, Object IDentifier) della visualizzazione tipizzata.|  
|VIEW_TYPE_OWNER|String|Il proprietario del tipo di visualizzazione, se questa è tipizzata.|  
|VIEW_TYPE|String|Tipo di visualizzazione, se questa è tipizzata.|  
|SUPERVIEW_NAME|String|Nome della superview.|  
  
## <a name="functions"></a>Funzioni  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'oggetto.|  
|OBJECT_NAME|String|Nome dell'oggetto.|  
|SUBOBJECT_NAME|String|Nome del sottoggetto, ad esempio una partizione.|  
|OBJECT_ID|Decimal|Il numero dell'oggetto dizionario dell'oggetto.|  
|DATA_OBJECT_ID|Decimal|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|  
|OBJECT_TYPE|String|Il tipo di oggetto.|  
|CREATED|DateTime|Data di creazione dell'oggetto.|  
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|  
|TIMESTAMP|String|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|  
|STATO|String|Lo stato dell'oggetto (VALID, INVALID o N/A).|  
|TEMPORARY|String|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|  
|GENERATED|String|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|  
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|  
  
## <a name="packages"></a>Pacchetti  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'oggetto.|  
|OBJECT_NAME|String|Nome dell'oggetto.|  
|SUBOBJECT_NAME|String|Nome del sottoggetto, ad esempio una partizione.|  
|OBJECT_ID|Decimal|Il numero dell'oggetto dizionario dell'oggetto.|  
|DATA_OBJECT_ID|Decimal|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|  
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|  
|TIMESTAMP|String|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|  
|STATO|String|Lo stato dell'oggetto (VALID, INVALID o N/A).|  
|TEMPORARY|String|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|  
|GENERATED|String|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|  
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|  
|CREATED|DateTime|Data di creazione dell'oggetto.|  
  
## <a name="packagebodies"></a>PackageBodies  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'oggetto.|  
|OBJECT_NAME|String|Nome dell'oggetto.|  
|SUBOBJECT_NAME|String|Nome del sottoggetto, ad esempio una partizione.|  
|OBJECT_ID|Decimal|Il numero dell'oggetto dizionario dell'oggetto.|  
|DATA_OBJECT_ID|Decimal|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|  
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|  
|TIMESTAMP|String|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|  
|STATO|String|Lo stato dell'oggetto (VALID, INVALID o N/A).|  
|TEMPORARY|String|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|  
|GENERATED|String|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|  
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|  
|CREATED|DateTime|Data di creazione dell'oggetto.|  
  
## <a name="arguments"></a>Argomenti  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Nome del proprietario dell'oggetto.|  
|PACKAGE_NAME|String|Il nome del package.|  
|OBJECT_NAME|String|Nome della routine o funzione.|  
|ARGUMENT_NAME|String|Il nome dell'argomento.|  
|POSITION|Decimal|Posizione nell'elenco degli argomenti o NULL per il valore restituito di una funzione.|  
|SEQUENCE|Decimal|La sequenza di argomenti, inclusi tutti i livelli di annidamento.|  
|DEFAULT_VALUE|String|Valore predefinito dell'argomento.|  
|DEFAULT_LENGTH|Decimal|La lunghezza del valore predefinito dell'argomento.|  
|IN_OUT|String|La direzione dell'argomento (IN, OUT o IN/OUT).|  
|DATA_LENGTH|Decimal|Lunghezza della colonna in byte.|  
|DATA_PRECISION|Decimal|La lunghezza in cifre decimali (NUMBER) o bit (FLOAT).|  
|DATA_SCALE|Decimal|Cifre a destra del separatore decimale in un numero.|  
|DATA_TYPE|String|Tipo di dati dell'argomento.|  
  
## <a name="uniquekeys"></a>UniqueKeys  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della definizione del vincolo.|  
|CONSTRAINT_NAME|String|Il nome della definizione del vincolo.|  
|TABLE_NAME|String|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|  
|SEARCH_CONDITION|String|Il testo della condizione di ricerca per un vincolo CHECK.|  
|R_OWNER|String|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|  
|R_CONSTRAINT_NAME|String|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|  
|DELETE_RULE|String|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|  
|STATO|String|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|  
|DEFERRABLE|String|Specifica se il vincolo può essere rinviato.|  
|VALIDATED|String|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|  
|GENERATED|String|Indica se il nome del vincolo è generato dall'utente o dal sistema.|  
|BAD|String|Il valore YES indica che nel vincolo un secolo è specificato in modo ambiguo. Per evitare errori provocati da tale ambiguità, scrivere nuovamente il vincolo usando la funzione TO_DATE con un anno di quattro cifre.|  
|RELY|String|Indica se è applicato un vincolo ENABLED.|  
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|  
|INDEX_OWNER|String|Nome dell'utente proprietario dell'indice.|  
|INDEX_NAME|String|Nome dell'indice.|  
  
## <a name="primarykeys"></a>PrimaryKeys  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della definizione del vincolo.|  
|CONSTRAINT_NAME|String|Il nome della definizione del vincolo.|  
|TABLE_NAME|String|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|  
|SEARCH_CONDITION|String|Il testo della condizione di ricerca per un vincolo CHECK.|  
|R_OWNER|String|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|  
|R_CONSTRAINT_NAME|String|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|  
|DELETE_RULE|String|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|  
|STATO|String|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|  
|DEFERRABLE|String|Specifica se il vincolo può essere rinviato.|  
|VALIDATED|String|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|  
|GENERATED|String|Indica se il nome del vincolo è generato dall'utente o dal sistema.|  
|BAD|String|Il valore YES indica che nel vincolo un secolo è specificato in modo ambiguo. Per evitare errori provocati da tale ambiguità, scrivere nuovamente il vincolo usando la funzione TO_DATE con un anno di quattro cifre.|  
|RELY|String|Indica se è applicato un vincolo ENABLED.|  
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|  
|INDEX_OWNER|String|Nome dell'utente proprietario dell'indice.|  
|INDEX_NAME|String|Nome dell'indice.|  
  
## <a name="foreignkeys"></a>ForeignKeys  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|PRIMARY_KEY_CONSTRAINT_NAME|String|Il nome della definizione del vincolo.|  
|PRIMARY_KEY_OWNER|String|Proprietario della definizione del vincolo.|  
|PRIMARY_KEY_TABLE_NAME|String|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|  
|FOREIGN_KEY_OWNER|String|Proprietario della definizione del vincolo.|  
|FOREIGN_KEY_CONSTRAINT_NAME|String|Il nome della definizione del vincolo.|  
|FOREIGN_KEY_TABLE_NAME|String|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|  
|SEARCH_CONDITION|String|Il testo della condizione di ricerca per un vincolo CHECK.|  
|R_OWNER|String|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|  
|R_CONSTRAINT_NAME|String|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|  
|DELETE_RULE|String|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|  
|STATO|String|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|  
|VALIDATED|String|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|  
|GENERATED|String|Indica se il nome del vincolo è generato dall'utente o dal sistema.|  
|RELY|String|Indica se è applicato un vincolo ENABLED.|  
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|  
|INDEX_OWNER|String|Nome dell'utente proprietario dell'indice.|  
|INDEX_NAME|String|Nome dell'indice.|  
  
## <a name="foreignkeycolumns"></a>ForeignKeyColumns  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario della definizione del vincolo.|  
|CONSTRAINT_NAME|String|Il nome della definizione del vincolo.|  
|TABLE_NAME|String|Il nome della tabella con la definizione del vincolo.|  
|COLUMN_NAME|String|Il nome della colonna o dell'attributo della colonna del tipo oggetto specificata nella definizione del vincolo.|  
|POSITION|Decimal|Posizione originale della colonna o dell'attributo nella definizione dell'oggetto.|  
  
## <a name="procedureparameters"></a>ProcedureParameters  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|OWNER|String|Proprietario dell'oggetto.|  
|OBJECT_NAME|String|Nome della routine o funzione.|  
|PACKAGE_NAME|String|Nome della routine o funzione.|  
|OBJECT_ID|Decimal|Il numero di oggetto dell'oggetto.|  
|OVERLOAD|String|Identificatore univoco dell'overload.|  
|ARGUMENT_NAME|String|Il nome dell'argomento.|  
|POSITION|Decimal|Posizione nell'elenco degli argomenti o NULL per il valore restituito di una funzione.|  
|SEQUENCE|Decimal|La sequenza di argomenti, inclusi tutti i livelli di annidamento.|  
|DATA_LEVEL|Decimal|Il livello di annidamento dell'argomento per i tipi composti.|  
|DATA_TYPE|String|Tipo di dati dell'argomento.|  
|DEFAULT_VALUE|String|Valore predefinito dell'argomento.|  
|DEFAULT_LENGTH|Decimal|La lunghezza del valore predefinito dell'argomento.|  
|IN_OUT|String|La direzione dell'argomento (IN, OUT o IN/OUT).|  
|DATA_LENGTH|Decimal|La lunghezza della colonna in byte.|  
|DATA_PRECISION|Decimal|La lunghezza in cifre decimali (NUMBER) o bit (FLOAT).|  
|DATA_SCALE|Decimal|Le cifre a destra della virgola decimale in un numero.|  
|RADIX|Decimal|La base di un argomento per un numero.|  
|CHARACTER_SET_NAME|String|Il nome del set di caratteri per l'argomento.|  
|TYPE_OWNER|String|Il proprietario del tipo dell'argomento.|  
|TYPE_NAME|String|Nome del tipo dell'argomento. Se il tipo è un tipo locale di package, ovvero se è dichiarato in una specifica di package, in questa colonna verrà visualizzato il nome del package.|  
|TYPE_SUBNAME|String|È rilevante solo per i tipi locali di package. Viene visualizzato il nome del tipo che è dichiarato nel package identificato nella colonna TYPE_NAME.|  
|TYPE_LINK|String|È rilevante solo per i tipi locali di package quando il package identificato nella colonna TYPE_NAME è un package remoto. In questa colonna viene visualizzato il collegamento al database usato per fare riferimento al package remoto.|  
|PLS_TYPE|String|Per argomenti numerici, il nome del tipo PL/SQL dell'argomento. In caso contrario, il valore è NULL.|  
|CHAR_LENGTH|Decimal|Il limite dei caratteri per i dati di tipo stringa.|  
|CHAR_USED|String|Indica se il limite di byte (B) o il limite di caratteri (C) è ufficiale per la stringa.|  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
