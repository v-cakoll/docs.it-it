---
title: Raccolte di schemi Oracle
ms.date: 03/30/2017
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
ms.openlocfilehash: 016a21b2106e955fd9806c5fb62833bc37da1f2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878475"
---
# <a name="oracle-schema-collections"></a>Raccolte di schemi Oracle

Il provider di dati Microsoft .NET Framework per Oracle, oltre alle raccolte di schemi comuni, supporta le seguenti raccolte di schemi specifici:

- Colonne

- Indexes

- IndexColumns

- Procedure

- Sequenze

- Synonyms

- Tabelle

- Utenti

- Visualizzazioni

- Funzioni

- Pacchetti

- PackageBodies

- Argomenti

- UniqueKeys

- PrimaryKeys

- ForeignKeys

- ForeignKeyColumns

- ProcedureParameters

## <a name="columns"></a>Colonne

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della tabella, della visualizzazione o del cluster.|
|TABLE_NAME|Stringa|Nome della tabella, della visualizzazione o del cluster.|
|COLUMN_NAME|Stringa|Nome della colonna.|
|Id|Decimale|Numero di sequenza della colonna in base all'ordine in cui vengono create le colonne.|
|DATATYPE|Stringa|Tipo di dati della colonna.|
|LENGTH|Decimale|Lunghezza della colonna in byte.|
|PRECISION|Decimale|Precisione decimale per il tipo di dati NUMBER e precisione binaria per il tipo di dati FLOAT. Per tutti gli altri tipi di dati, il valore è null.|
|SCALE|Decimale|Cifre a destra del separatore decimale in un numero.|
|NULLABLE|Stringa|Specifica se una colonna supporta i valori NULL. Il valore è N se è presente un vincolo diverso da NULL sulla colonna o se la colonna fa parte di un vincolo PRIMARY KEY.|

## <a name="indexes"></a>Indexes

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'indice.|
|INDEX_NAME|Stringa|Nome dell'indice.|
|INDEX_TYPE|Stringa|Tipo di indice (NORMAL, BITMAP, FUNCTION-BASED NORMAL, FUNCTION-BASED BITMAP o DOMAIN).|
|TABLE_OWNER|Stringa|Proprietario dell'oggetto indicizzato.|
|TABLE_NAME|Stringa|Nome dell'oggetto indicizzato.|
|TABLE_TYPE|Stringa|Tipo di oggetto indicizzato, ad esempio TABLE e CLUSTER.|
|UNIQUENESS|Stringa|Se l'indice è UNIQUE o NONUNIQUE.|
|COMPRESSION|Stringa|Se l'indice è ENABLED o DISABLED.|
|PREFIX_LENGTH|Decimale|Il numero di colonne nel prefisso della chiave compression.|
|TABLESPACE_NAME|Stringa|Il nome dello spazio di tabella contenente l'indice.|
|INI_TRANS|Decimale|Il numero iniziale di transazioni.|
|MAX_TRANS|Decimale|Il numero massimo di transazioni.|
|INITIAL_EXTENT|Decimale|La dimensione dell'extent iniziale.|
|NEXT_EXTENT|Decimale|Dimensione degli extent successivi.|
|MIN_EXTENTS|Decimale|Numero minimo di extent consentito nel segmento.|
|MAX_EXTENTS|Decimale|Il numero massimo di extent consentito nel segmento.|
|PCT_INCREASE|Decimale|La percentuale di aumento della dimensione degli extent.|
|PCT_THRESHOLD|Decimale|La soglia percentuale di spazio dei blocchi consentita in base alla voce dell'indice.|
|INCLUDE_COLUMN|Decimale|L'identificatore colonna dell'ultima colonna da includere nell'indice (non overflow) della chiave primaria della tabella con indice. Il mapping di questa colonna viene eseguito alla colonna COLUMN_ID delle visualizzazioni del dizionario dei dati *_TAB_COLUMNS.|
|FREELISTS|Decimale|Il numero di elenchi di disponibilità di processi allocato al segmento.|
|FREELIST_GROUPS|Decimale|Il numero di elenchi di disponibilità di gruppi allocato al segmento.|
|PCT_FREE|Decimale|Percentuale minima di spazio disponibile in un blocco.|
|LOGGING|Stringa|Le informazioni sulla registrazione.|
|BLEVEL|Decimale|Livello dell'albero B*: profondità dell'indice dal blocco radice ai relativi blocchi foglia. La profondità 0 indica che il blocco radice e il blocco foglia sono identici.|
|LEAF_BLOCKS|Decimale|Il numero di blocchi foglia nell'indice.|
|DISTINCT_KEYS|Decimale|Il numero di valori indicizzati distinti. Per gli indici che impongono i vincoli UNIQUE e PRIMARY KEY, questo valore corrisponde al numero di righe nella tabella (USER_TABLES.NUM_ROWS).|
|AVG_LEAF_BLOCKS_PER_KEY|Decimale|Il numero medio dei blocchi foglia in cui ciascun valore distinct dell'indice viene arrotondato al valore integer più vicino. Per gli indici che impongono i vincoli UNIQUE e PRIMARY KEY, questo valore è sempre 1.|
|AVG_DATA_BLOCKS_PER_KEY|Decimale|Il numero medio dei blocchi di dati nella tabella a cui fa riferimento un valore distinct dell'indice arrotondato al valore integer più vicino. Questa statistica rappresenta il numero medio dei blocchi di dati contenenti righe in cui è presente un valore specificato per le colonne indicizzate.|
|CLUSTERING_FACTOR|Decimale|Indica il livello di ordine delle righe nella tabella in base ai valori dell'indice.|
|STATO|Stringa|Indica se un indice non partizionato è VALID o UNUSABLE.|
|NUM_ROWS|Decimale|Il numero di righe dell'indice.|
|SAMPLE_SIZE|Decimale|Dimensione dell'esempio usato per analizzare l'indice.|
|LAST_ANALYZED|DateTime|La data più recente in cui è stato analizzato l'indice.|
|DEGREE|Stringa|Il numero di thread per ogni istanza per l'analisi dell'indice.|
|INSTANCES|Stringa|Il numero di istanze in cui analizzare gli indici.|
|PARTITIONED|Stringa|Indica se l'indice è partizionato (YES &#124; NO).|
|TEMPORARY|Stringa|Indica se l'indice è in una tabella temporanea.|
|GENERATED|Stringa|Se il nome dell'indice è generato dal sistema (Y&#124;N).|
|SECONDARY|Stringa|Indica se l'indice è un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y&#124;N).|
|BUFFER_POOL|Stringa|Il nome del pool di buffer predefinito da usare per il blocchi dell'indice.|
|USER_STATS|Stringa|Indica se le statistiche sono state immesse direttamente dall'utente.|
|DURATION|Stringa|Indica la durata di una tabella temporanea: 1) SYS$ SESSION: le righe vengono mantenute per tutta la durata della sessione, 2) SYS$ TRANSACTION: le righe vengono eliminate dopo il COMMIT, 3) Null per una tabella permanente.|
|PCT_DIRECT_ACCESS|Decimale|Indica la percentuale di righe con guess uguale a VALID per un indice secondario in una tabella con indice.|
|ITYP_OWNER|Stringa|Indica il proprietario del tipo di indice per un indice di dominio.|
|ITYP_NAME|Stringa|Indica il nome del tipo di indice per un indice di dominio.|
|PARAMETERS|Stringa|Indica la stringa del parametro per un indice di dominio.|
|GLOBAL_STATS|Stringa|Per gli indici partizionati, indica se le statistiche sono state raccolte analizzando l'intero indice (YES) o se sono state valutate in base alle statistiche sulle partizioni e sottopartizioni dell'indice sottostanti (NO).|
|DOMIDX_STATUS|Stringa|Riflette lo stato dell'indice di dominio. NULL: l'indice specificato non è un indice di dominio. VALID: l'indice è un indice di dominio valido. IDXTYP_INVLD: il tipo di indice dell'indice di dominio non è valido.|
|DOMIDX_OPSTATUS|Stringa|Riflette lo stato di un'operazione eseguita su un indice di dominio. NULL: l'indice specificato non è un indice di dominio. VALID: l'operazione è stata eseguita senza errori. FAILED: si è verificato un errore e l'operazione non è stata eseguita correttamente.|
|FUNCIDX_STATUS|Stringa|Indica lo stato di un indice basato su funzioni. NULL: questo non è basato sulla funzione di indice, abilitato: l'indice basato sulla funzione è abilitato, DISABILITATO: l'indice basato su funzioni è disabilitato.|
|JOIN_INDEX|Stringa|Indica se l'indice è un indice di join o meno.|

## <a name="indexcolumns"></a>IndexColumns

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|INDEX_OWNER|Stringa|Proprietario dell'indice.|
|INDEX_NAME|Stringa|Nome dell'indice.|
|TABLE_OWNER|Stringa|Proprietario della tabella o del cluster.|
|TABLE_NAME|Stringa|Nome della tabella o del cluster.|
|COLUMN_NAME|Stringa|Nome della colonna o attributo della colonna del tipo oggetto.|
|COLUMN_POSITION|Decimale|La posizione della colonna o dell'attributo all'interno dell'indice.|
|COLUMN_LENGTH|Decimale|La lunghezza indicizzata della colonna.|
|CHAR_LENGTH|Decimale|La lunghezza massima dei punti di codice della colonna.|
|DESCEND|Stringa|Indica se la colonna è ordinata in ordine decrescente.|

## <a name="procedures"></a>Procedure

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'oggetto.|
|OBJECT_NAME|Stringa|Nome dell'oggetto.|
|SUBOBJECT_NAME|Stringa|Nome del sottoggetto, ad esempio una partizione.|
|OBJECT_ID|Decimale|Il numero dell'oggetto dizionario dell'oggetto.|
|DATA_OBJECT_ID|Decimale|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|
|TIMESTAMP|Stringa|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|
|STATO|Stringa|Lo stato dell'oggetto (VALID, INVALID o N/A).|
|TEMPORARY|Stringa|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|
|GENERATED|Stringa|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|
|CREATED|DateTime|Data di creazione dell'oggetto.|

## <a name="sequences"></a>Sequenze

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|SEQUENCE_OWNER|Stringa|Nome del proprietario della sequenza.|
|SEQUENCE_NAME|Stringa|Il nome della sequenza.|
|MIN_VALUE|Decimale|Valore minimo della sequenza.|
|MAX_VALUE|Decimale|Valore massimo della sequenza.|
|INCREMENT_BY|Decimale|Il valore dell'incremento della sequenza.|
|CYCLE_FLAG|Stringa|Indica se la sequenza è prossima al raggiungimento del limite.|
|ORDER_FLAG|Stringa|Indica se i numeri di sequenza sono generati in ordine.|
|CACHE_SIZE|Decimale|Il numero dei numeri di sequenza da memorizzare nella cache.|
|LAST_NUMBER|Decimale|L'ultimo numero di sequenza scritto sul disco. Se per una sequenza viene usata la memorizzazione nella cache, il numero scritto sul disco corrisponde all'ultimo numero inserito nella cache delle sequenze. È probabile che questo numero sia maggiore dell'ultimo numero di sequenza usato.|

## <a name="synonyms"></a>Synonyms

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario del sinonimo.|
|SYNONYM_NAME|Stringa|Nome del sinonimo.|
|TABLE_OWNER|Stringa|Proprietario dell'oggetto a cui fa riferimento il sinonimo.|
|TABLE_NAME|Stringa|Il nome dell'oggetto a cui fa riferimento il sinonimo.|
|DB_LINK|Stringa|Nome del collegamento al database a cui viene fatto riferimento, se presente.|

## <a name="tables"></a>Tabelle

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della tabella.|
|TABLE_NAME|Stringa|Nome della tabella.|
|TYPE|Stringa|Tipo di tabella.|

## <a name="users"></a>Utenti

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|NAME|Stringa|Nome dell'utente.|
|Id|Decimale|Numero ID dell'utente.|
|CREATEDATE|DateTime|Data di creazione dell'utente.|

## <a name="views"></a>Visualizzazioni

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della visualizzazione.|
|VIEW_NAME|Stringa|Nome della visualizzazione.|
|TEXT_LENGTH|Decimale|Lunghezza del testo della visualizzazione.|
|TEXT|Stringa|Testo della visualizzazione.|
|TYPE_TEXT_LENGTH|Decimale|Lunghezza della clausola di tipo della visualizzazione tipizzata.|
|TYPE_TEXT|Stringa|La clausola di tipo della visualizzazione tipizzata.|
|OID_TEXT_LENGTH|Decimale|La lunghezza della clausola con l'identificatore di oggetto (OID, Object IDentifier) della visualizzazione tipizzata.|
|OID_TEXT|Stringa|La clausola con l'identificatore di oggetto (OID, Object IDentifier) della visualizzazione tipizzata.|
|VIEW_TYPE_OWNER|Stringa|Il proprietario del tipo di visualizzazione, se questa è tipizzata.|
|VIEW_TYPE|Stringa|Tipo di visualizzazione, se questa è tipizzata.|
|SUPERVIEW_NAME|Stringa|Nome della superview.|

## <a name="functions"></a>Funzioni

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'oggetto.|
|OBJECT_NAME|Stringa|Nome dell'oggetto.|
|SUBOBJECT_NAME|Stringa|Nome del sottoggetto, ad esempio una partizione.|
|OBJECT_ID|Decimale|Il numero dell'oggetto dizionario dell'oggetto.|
|DATA_OBJECT_ID|Decimale|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|
|OBJECT_TYPE|Stringa|Il tipo di oggetto.|
|CREATED|DateTime|Data di creazione dell'oggetto.|
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|
|TIMESTAMP|Stringa|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|
|STATO|Stringa|Lo stato dell'oggetto (VALID, INVALID o N/A).|
|TEMPORARY|Stringa|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|
|GENERATED|Stringa|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|

## <a name="packages"></a>Pacchetti

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'oggetto.|
|OBJECT_NAME|Stringa|Nome dell'oggetto.|
|SUBOBJECT_NAME|Stringa|Nome del sottoggetto, ad esempio una partizione.|
|OBJECT_ID|Decimale|Il numero dell'oggetto dizionario dell'oggetto.|
|DATA_OBJECT_ID|Decimale|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|
|TIMESTAMP|Stringa|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|
|STATO|Stringa|Lo stato dell'oggetto (VALID, INVALID o N/A).|
|TEMPORARY|Stringa|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|
|GENERATED|Stringa|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|
|CREATED|DateTime|Data di creazione dell'oggetto.|

## <a name="packagebodies"></a>PackageBodies

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'oggetto.|
|OBJECT_NAME|Stringa|Nome dell'oggetto.|
|SUBOBJECT_NAME|Stringa|Nome del sottoggetto, ad esempio una partizione.|
|OBJECT_ID|Decimale|Il numero dell'oggetto dizionario dell'oggetto.|
|DATA_OBJECT_ID|Decimale|Numero dell'oggetto dizionario del segmento contenente l'oggetto.|
|LAST_DDL_TIME|DateTime|Il timestamp per l'ultima modifica dell'oggetto, risultante da un comando DDL (Database Definition Language), incluse le concessioni e le revoche.|
|TIMESTAMP|Stringa|Il timestamp per la specifica dell'oggetto (dati di tipo carattere).|
|STATO|Stringa|Lo stato dell'oggetto (VALID, INVALID o N/A).|
|TEMPORARY|Stringa|Indica se l'oggetto è temporaneo (la sessione corrente è in grado di visualizzare solo i dati inseriti nell'oggetto stesso).|
|GENERATED|Stringa|Indica se il nome dell'oggetto è stato generato dal sistema. (Y &#124; N).|
|SECONDARY|Stringa|Se si tratta di un oggetto secondario creato dal metodo ODCIIndexCreate di Oracle9i Data Cartridge (Y &#124; N).|
|CREATED|DateTime|Data di creazione dell'oggetto.|

## <a name="arguments"></a>Argomenti

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Nome del proprietario dell'oggetto.|
|PACKAGE_NAME|Stringa|Il nome del package.|
|OBJECT_NAME|Stringa|Nome della routine o funzione.|
|ARGUMENT_NAME|Stringa|Il nome dell'argomento.|
|POSITION|Decimale|Posizione nell'elenco degli argomenti o NULL per il valore restituito di una funzione.|
|SEQUENCE|Decimale|La sequenza di argomenti, inclusi tutti i livelli di annidamento.|
|DEFAULT_VALUE|Stringa|Valore predefinito dell'argomento.|
|DEFAULT_LENGTH|Decimale|La lunghezza del valore predefinito dell'argomento.|
|IN_OUT|Stringa|La direzione dell'argomento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimale|Lunghezza della colonna in byte.|
|DATA_PRECISION|Decimale|La lunghezza in cifre decimali (NUMBER) o bit (FLOAT).|
|DATA_SCALE|Decimale|Cifre a destra del separatore decimale in un numero.|
|DATA_TYPE|Stringa|Tipo di dati dell'argomento.|

## <a name="uniquekeys"></a>UniqueKeys

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della definizione del vincolo.|
|CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo.|
|TABLE_NAME|Stringa|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|
|SEARCH_CONDITION|Stringa|Il testo della condizione di ricerca per un vincolo CHECK.|
|R_OWNER|Stringa|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|
|R_CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|
|DELETE_RULE|Stringa|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|
|STATO|Stringa|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|
|DEFERRABLE|Stringa|Specifica se il vincolo può essere rinviato.|
|VALIDATED|Stringa|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|
|GENERATED|Stringa|Indica se il nome del vincolo è generato dall'utente o dal sistema.|
|BAD|Stringa|Il valore YES indica che nel vincolo un secolo è specificato in modo ambiguo. Per evitare errori provocati da tale ambiguità, scrivere nuovamente il vincolo usando la funzione TO_DATE con un anno di quattro cifre.|
|RELY|Stringa|Indica se è applicato un vincolo ENABLED.|
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|
|INDEX_OWNER|Stringa|Nome dell'utente proprietario dell'indice.|
|INDEX_NAME|Stringa|Nome dell'indice.|

## <a name="primarykeys"></a>PrimaryKeys

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della definizione del vincolo.|
|CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo.|
|TABLE_NAME|Stringa|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|
|SEARCH_CONDITION|Stringa|Il testo della condizione di ricerca per un vincolo CHECK.|
|R_OWNER|Stringa|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|
|R_CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|
|DELETE_RULE|Stringa|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|
|STATO|Stringa|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|
|DEFERRABLE|Stringa|Specifica se il vincolo può essere rinviato.|
|VALIDATED|Stringa|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|
|GENERATED|Stringa|Indica se il nome del vincolo è generato dall'utente o dal sistema.|
|BAD|Stringa|Il valore YES indica che nel vincolo un secolo è specificato in modo ambiguo. Per evitare errori provocati da tale ambiguità, scrivere nuovamente il vincolo usando la funzione TO_DATE con un anno di quattro cifre.|
|RELY|Stringa|Indica se è applicato un vincolo ENABLED.|
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|
|INDEX_OWNER|Stringa|Nome dell'utente proprietario dell'indice.|
|INDEX_NAME|Stringa|Nome dell'indice.|

## <a name="foreignkeys"></a>ForeignKeys

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|PRIMARY_KEY_CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo.|
|PRIMARY_KEY_OWNER|Stringa|Proprietario della definizione del vincolo.|
|PRIMARY_KEY_TABLE_NAME|Stringa|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|
|FOREIGN_KEY_OWNER|Stringa|Proprietario della definizione del vincolo.|
|FOREIGN_KEY_CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo.|
|FOREIGN_KEY_TABLE_NAME|Stringa|Il nome associato alla tabella (o visualizzazione) con la definizione del vincolo.|
|SEARCH_CONDITION|Stringa|Il testo della condizione di ricerca per un vincolo CHECK.|
|R_OWNER|Stringa|Il proprietario della tabella a cui viene fatto riferimento in un vincolo referenziale.|
|R_CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo UNIQUE per la tabella a cui viene fatto riferimento.|
|DELETE_RULE|Stringa|La regola di eliminazione per un vincolo referenziale (CASCADE o NO ACTION).|
|STATO|Stringa|Lo stato di attivazione del vincolo (ENABLED o DISABLED).|
|VALIDATED|Stringa|Indica se tutti i dati sono conformi al vincolo (VALIDATED o NOT VALIDATED).|
|GENERATED|Stringa|Indica se il nome del vincolo è generato dall'utente o dal sistema.|
|RELY|Stringa|Indica se è applicato un vincolo ENABLED.|
|LAST_CHANGE|DateTime|Indica l'ultima abilitazione o disabilitazione del vincolo.|
|INDEX_OWNER|Stringa|Nome dell'utente proprietario dell'indice.|
|INDEX_NAME|Stringa|Nome dell'indice.|

## <a name="foreignkeycolumns"></a>ForeignKeyColumns

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario della definizione del vincolo.|
|CONSTRAINT_NAME|Stringa|Il nome della definizione del vincolo.|
|TABLE_NAME|Stringa|Il nome della tabella con la definizione del vincolo.|
|COLUMN_NAME|Stringa|Il nome della colonna o dell'attributo della colonna del tipo oggetto specificata nella definizione del vincolo.|
|POSITION|Decimale|Posizione originale della colonna o dell'attributo nella definizione dell'oggetto.|

## <a name="procedureparameters"></a>ProcedureParameters

|Nome colonna|Tipo di dati|Descrizione|
|----------------|--------------|-----------------|
|OWNER|Stringa|Proprietario dell'oggetto.|
|OBJECT_NAME|Stringa|Nome della routine o funzione.|
|PACKAGE_NAME|Stringa|Nome della routine o funzione.|
|OBJECT_ID|Decimale|Il numero di oggetto dell'oggetto.|
|OVERLOAD|Stringa|Identificatore univoco dell'overload.|
|ARGUMENT_NAME|Stringa|Il nome dell'argomento.|
|POSITION|Decimale|Posizione nell'elenco degli argomenti o NULL per il valore restituito di una funzione.|
|SEQUENCE|Decimale|La sequenza di argomenti, inclusi tutti i livelli di annidamento.|
|DATA_LEVEL|Decimale|Il livello di annidamento dell'argomento per i tipi composti.|
|DATA_TYPE|Stringa|Tipo di dati dell'argomento.|
|DEFAULT_VALUE|Stringa|Valore predefinito dell'argomento.|
|DEFAULT_LENGTH|Decimale|La lunghezza del valore predefinito dell'argomento.|
|IN_OUT|Stringa|La direzione dell'argomento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimale|La lunghezza della colonna in byte.|
|DATA_PRECISION|Decimale|La lunghezza in cifre decimali (NUMBER) o bit (FLOAT).|
|DATA_SCALE|Decimale|Le cifre a destra della virgola decimale in un numero.|
|RADIX|Decimale|La base di un argomento per un numero.|
|CHARACTER_SET_NAME|Stringa|Il nome del set di caratteri per l'argomento.|
|TYPE_OWNER|Stringa|Il proprietario del tipo dell'argomento.|
|TYPE_NAME|Stringa|Nome del tipo dell'argomento. Se il tipo è un tipo locale di package, ovvero se è dichiarato in una specifica di package, in questa colonna verrà visualizzato il nome del package.|
|TYPE_SUBNAME|Stringa|È rilevante solo per i tipi locali di package. Viene visualizzato il nome del tipo che è dichiarato nel package identificato nella colonna TYPE_NAME.|
|TYPE_LINK|Stringa|È rilevante solo per i tipi locali di package quando il package identificato nella colonna TYPE_NAME è un package remoto. In questa colonna viene visualizzato il collegamento al database usato per fare riferimento al package remoto.|
|PLS_TYPE|Stringa|Per argomenti numerici, il nome del tipo PL/SQL dell'argomento. In caso contrario, il valore è NULL.|
|CHAR_LENGTH|Decimale|Il limite dei caratteri per i dati di tipo stringa.|
|CHAR_USED|Stringa|Indica se il limite di byte (B) o il limite di caratteri (C) è ufficiale per la stringa.|

## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
