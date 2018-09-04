---
title: Raccolte di schemi SQL Server
ms.date: 03/30/2017
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
ms.openlocfilehash: 7020c74d41ce1feef38c4dfc66117a7b8c8eff4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508490"
---
# <a name="sql-server-schema-collections"></a>Raccolte di schemi SQL Server
Il provider di dati Microsoft .NET Framework per SQL Server, oltre alle raccolta di schemi comuni, supporta la raccolta di schemi aggiuntivi. Le raccolte di schemi variano leggermente in base alla versione di SQL Server usata. Per determinare l'elenco di raccolte di schemi supportati, chiamare il **GetSchema** metodo senza argomenti oppure con il nome di raccolta di schemi "MetaDataCollections". In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco delle raccolte di schemi supportati, il numero delle restrizioni supportate da ciascuna raccolta e il numero di parti identificatore usate.  
  
## <a name="databases"></a>Database  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|database_name|String|Nome del database.|  
|dbid|Int16|Identificatore del database.|  
|create_date|DateTime|Data di creazione del database.|  
  
## <a name="foreign-keys"></a>Foreign Keys  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|CONSTRAINT_CATALOG|Stringa|Catalogo a cui appartiene il vincolo.|  
|CONSTRAINT_SCHEMA|Stringa|Schema contenente il vincolo.|  
|CONSTRAINT_NAME|Stringa|Il nome.|  
|TABLE_CATALOG|Stringa|Nome della tabella contenente il vincolo.|  
|TABLE_SCHEMA|Stringa|Schema contenente la tabella.|  
|TABLE_NAME|Stringa|Nome tabella|  
|CONSTRAINT_TYPE|Stringa|Tipo di vincolo. È consentito solo il tipo "FOREIGN KEY".|  
|IS_DEFERRABLE|Stringa|Specifica se il vincolo può essere rinviato. Restituisce NO.|  
|INITIALLY_DEFERRED|Stringa|Specifica se inizialmente il vincolo può essere rinviato. Restituisce NO.|  
  
## <a name="indexes"></a>Indexes  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|Catalogo a cui appartiene l'indice.|  
|constraint_schema|String|Schema contenente l'indice.|  
|constraint_name|String|Nome dell'indice.|  
|table_catalog|String|Nome della tabella a cui è associato l'indice.|  
|table_schema|String|Schema contenente la tabella a cui è associato l'indice.|  
|table_name|String|Nome della tabella.|  
|index_name|Stringa|Nome dell'indice.|  
  
### <a name="indexes-sql-server-2008"></a>Indexes (SQL Server 2008)  
 A partire da .NET Framework versione 3.5 SP1 e SQL Server 2008, le colonne seguenti sono state aggiunte alla raccolta di schemi Indexes per supportare nuovi tipi di dati spaziali, filestream e colonne di tipo sparse. Tali colonne non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|type_desc|String|I valori del tipo di indice sono i seguenti:<br /><br /> -HEAP<br />-CLUSTER<br />-NON CLUSTER<br />-   XML<br />-SPAZIALI|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|constraint_catalog|String|Catalogo a cui appartiene l'indice.|  
|constraint_schema|String|Schema contenente l'indice.|  
|constraint_name|String|Nome dell'indice.|  
|table_catalog|String|Nome della tabella a cui è associato l'indice.|  
|table_schema|String|Schema contenente la tabella a cui è associato l'indice.|  
|table_name|String|Nome della tabella.|  
|column_name|String|Nome della colonna a cui è associato l'indice.|  
|ordinal_position|Int32|Posizione ordinale della colonna.|  
|KeyType|Byte|Tipo di oggetto.|  
|index_name|Stringa|Nome dell'indice.|  
  
## <a name="procedures"></a>Procedure  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|Stringa|Nome specifico del catalogo.|  
|SPECIFIC_SCHEMA|Stringa|Il nome specifico dello schema.|  
|SPECIFIC_NAME|Stringa|Nome specifico del catalogo.|  
|ROUTINE_CATALOG|Stringa|Il catalogo a cui appartiene la stored procedure.|  
|ROUTINE_SCHEMA|Stringa|Lo schema contenente la stored procedure.|  
|ROUTINE_NAME|Stringa|Il nome della stored procedure.|  
|ROUTINE_TYPE|Stringa|Restituisce PROCEDURE per le stored procedure e FUNCTION per le funzioni.|  
|CREATED|DateTime|L'ora in cui è stata creata la routine.|  
|LAST_ALTERED|DateTime|Data e ora dell'ultima modifica della routine.|  
  
## <a name="procedure-parameters"></a>Procedure Parameters  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|Stringa|Nome del catalogo della routine per cui viene specificato questo parametro.|  
|SPECIFIC_SCHEMA|Stringa|Lo schema contenente la routine a cui appartiene questo parametro.|  
|SPECIFIC_NAME|Stringa|Il nome della routine contenente questo parametro.|  
|ORDINAL_POSITION|Int32|Posizione ordinale del parametro iniziando da 1. Per il valore restituito di una routine, è uguale a 0.|  
|PARAMETER_MODE|Stringa|Restituisce IN se è un parametro di input, OUT se è un parametro di output e INOUT se è un parametro di input/output.|  
|IS_RESULT|Stringa|Restituisce YES se indica il risultato di una routine che è una funzione. In caso contrario, restituisce NO.|  
|AS_LOCATOR|Stringa|Restituisce YES se dichiarato come indicatore di posizione. In caso contrario, restituisce NO.|  
|PARAMETER_NAME|Stringa|Nome del parametro. Restituisce NULL se corrisponde al valore restituito di una funzione.|  
|DATA_TYPE|Stringa|Il tipo di dati fornito dal sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|La lunghezza massima in caratteri per il tipo di dati carattere o binario. Per altri tipi di parametro, restituisce NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|La lunghezza massima in byte per il tipo di dati carattere o binario. Per altri tipi di parametro, restituisce NULL.|  
|COLLATION_CATALOG|Stringa|Il nome del catalogo per le regole di confronto del parametro. Se non è di tipo carattere, restituisce NULL.|  
|COLLATION_SCHEMA|Stringa|Restituisce sempre NULL.|  
|COLLATION_NAME|Stringa|Nome delle regole di confronto del parametro. Se non è di tipo carattere, restituisce NULL.|  
|CHARACTER_SET_CATALOG|Stringa|Il nome del catalogo del set di caratteri del parametro. Se non è di tipo carattere, restituisce NULL.|  
|CHARACTER_SET_SCHEMA|Stringa|Restituisce sempre NULL.|  
|CHARACTER_SET_NAME|Stringa|Nome del set di caratteri del parametro. Se non è di tipo carattere, restituisce NULL.|  
|NUMERIC_PRECISION|Byte|La precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di parametro, restituisce NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|La radice della precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di parametro, restituisce NULL.|  
|NUMERIC_SCALE|Int32|La scala dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di parametro, restituisce NULL.|  
|DATETIME_PRECISION|Int16|La precisione in secondi frazionari se il tipo di parametro è datetime oppure smalldatetime. Per altri tipi di parametro, restituisce NULL.|  
|INTERVAL_TYPE|Stringa|NULL. Riservato per un utilizzo futuro da parte di SQL Server.|  
|INTERVAL_PRECISION|Int16|NULL. Riservato per un utilizzo futuro da parte di SQL Server.|  
  
## <a name="tables"></a>Tabelle  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Stringa|Catalogo della tabella.|  
|TABLE_SCHEMA|Stringa|Schema contenente la tabella.|  
|TABLE_NAME|Stringa|Nome della tabella.|  
|TABLE_TYPE|Stringa|Tipo di tabella. Può essere VIEW o BASE TABLE.|  
  
## <a name="columns"></a>Colonne  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Stringa|Catalogo della tabella.|  
|TABLE_SCHEMA|Stringa|Schema contenente la tabella.|  
|TABLE_NAME|Stringa|Nome della tabella.|  
|COLUMN_NAME|String|Nome della colonna.|  
|ORDINAL_POSITION|Int32|Numero di identificazione della colonna.|  
|COLUMN_DEFAULT|Stringa|Il valore predefinito della colonna.|  
|IS_NULLABLE|Stringa|Supporto di valori Null della colonna. Se la colonna supporta i valori NULL, restituisce YES. In caso contrario, restituisce NO.|  
|DATA_TYPE|Stringa|Il tipo di dati fornito dal sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32 – Sql8, Int16 – Sql7|La lunghezza massima in caratteri per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_OCTET_LENGTH|Int32 – SQL8, Int16 – Sql7|La lunghezza massima in byte per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION|Unsigned Byte|La precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|La radice della precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_SCALE|Int32|La scala dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|DATETIME_PRECISION|Int16|Il codice Subtype per datetime e per i tipi di dati dell'intervallo di SQL-92. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui è posizionato il set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_SCHEMA|Stringa|Restituisce sempre NULL.|  
|CHARACTER_SET_NAME|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito il nome univoco del set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|COLLATION_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui sono definite le regole di confronto. In caso contrario, il valore di questa colonna è NULL.|  
  
### <a name="columns-sql-server-2008"></a>Columns (SQL Server 2008)  
 A partire da .NET Framework versione 3.5 SP1 e SQL Server 2008, le colonne seguenti sono state aggiunte alla raccolta di schemi Columns per supportare nuovi tipi di dati spaziali, filestream e colonne di tipo sparse. Tali colonne non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|IS_FILESTREAM|String|YES in caso di colonna con attributo FILESTREAM.<br /><br /> NO se la colonna non dispone dell'attributo FILESTREAM.|  
|IS_SPARSE|String|YES in caso di colonna di tipo sparse.<br /><br /> NO se la colonna non è di tipo sparse.|  
|IS_COLUMN_SET|String|YES in caso di colonna del set di colonne.<br /><br /> NO se la colonna non fa parte del set di colonne.|  
  
### <a name="allcolumns-sql-server-2008"></a>AllColumns (SQL Server 2008)  
 A partire da .NET Framework versione 3.5 SP1 e SQL Server 2008, è stata aggiunta la raccolta di schemi AllColumns per supportare colonne di tipo sparse. AllColumns non è supportato nelle versioni precedenti di .NET Framework e di SQL Server.  
  
 AllColumns dispone delle stesse restrizioni e dello schema DataTable risultante della raccolta di schemi Columns, l'unica differenza è costituita dal fatto che AllColumns include colonne del set di colonne che non sono incluse nella raccolta di schemi Columns. Nella tabella seguente vengono descritte queste colonne.  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Stringa|Catalogo della tabella.|  
|TABLE_SCHEMA|Stringa|Schema contenente la tabella.|  
|TABLE_NAME|Stringa|Nome della tabella.|  
|COLUMN_NAME|String|Nome della colonna.|  
|ORDINAL_POSITION|Int32|Numero di identificazione della colonna.|  
|COLUMN_DEFAULT|Stringa|Il valore predefinito della colonna.|  
|IS_NULLABLE|Stringa|Supporto di valori Null della colonna. Se la colonna supporta i valori NULL, restituisce YES. In caso contrario, restituisce NO.|  
|DATA_TYPE|Stringa|Il tipo di dati fornito dal sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|La lunghezza massima in caratteri per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|La lunghezza massima in byte per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION|Unsigned Byte|La precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|La radice della precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_SCALE|Int32|La scala dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|DATETIME_PRECISION|Int16|Il codice Subtype per datetime e per i tipi di dati dell'intervallo di SQL-92. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui è posizionato il set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_SCHEMA|Stringa|Restituisce sempre NULL.|  
|CHARACTER_SET_NAME|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito il nome univoco del set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|COLLATION_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui sono definite le regole di confronto. In caso contrario, il valore di questa colonna è NULL.|  
|IS_FILESTREAM|String|YES in caso di colonna con attributo FILESTREAM.<br /><br /> NO se la colonna non dispone dell'attributo FILESTREAM.|  
|IS_SPARSE|String|YES in caso di colonna di tipo sparse.<br /><br /> NO se la colonna non è di tipo sparse.|  
|IS_COLUMN_SET|String|YES in caso di colonna del set di colonne.<br /><br /> NO se la colonna non fa parte del set di colonne.|  
  
### <a name="columnsetcolumns-sql-server-2008"></a>ColumnSetColumns (SQL Server 2008)  
 A partire da .NET Framework versione 3.5 SP1 e SQL Server 2008, è stata aggiunta la raccolta di schemi ColumnSetColumns per supportare colonne di tipo sparse. ColumnSetColumns non è supportato nelle versioni precedenti di .NET Framework e di SQL Server. La raccolta di schemi ColumnSetColumns restituisce lo schema per tutte le colonne di un set di colonne. Nella tabella seguente vengono descritte queste colonne.  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Stringa|Catalogo della tabella.|  
|TABLE_SCHEMA|Stringa|Schema contenente la tabella.|  
|TABLE_NAME|Stringa|Nome della tabella.|  
|COLUMN_NAME|String|Nome della colonna.|  
|ORDINAL_POSITION|Int32|Numero di identificazione della colonna.|  
|COLUMN_DEFAULT|Stringa|Il valore predefinito della colonna.|  
|IS_NULLABLE|Stringa|Supporto di valori Null della colonna. Se la colonna supporta i valori NULL, restituisce YES. In caso contrario, restituisce NO.|  
|DATA_TYPE|Stringa|Il tipo di dati fornito dal sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|La lunghezza massima in caratteri per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|La lunghezza massima in byte per i tipi di dati binario e carattere o per i tipi di dati testo e immagine. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION|Unsigned Byte|La precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|La radice della precisione dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|NUMERIC_SCALE|Int32|La scala dei dati numerici approssimativi, dei dati numerici esatti, dei dati di tipo integer o dei dati di tipo valuta. Per altri tipi di dati, viene restituito NULL.|  
|DATETIME_PRECISION|Int16|Il codice Subtype per datetime e per i tipi di dati dell'intervallo di SQL-92. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui è posizionato il set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|CHARACTER_SET_SCHEMA|Stringa|Restituisce sempre NULL.|  
|CHARACTER_SET_NAME|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito il nome univoco del set di caratteri. Per altri tipi di dati, viene restituito NULL.|  
|COLLATION_CATALOG|Stringa|Se la colonna presenta un tipo di dati carattere o testo, viene restituito master, che indica il database in cui sono definite le regole di confronto. In caso contrario, il valore di questa colonna è NULL.|  
|IS_FILESTREAM|String|YES in caso di colonna con attributo FILESTREAM.<br /><br /> NO se la colonna non dispone dell'attributo FILESTREAM.|  
|IS_SPARSE|String|YES in caso di colonna di tipo sparse.<br /><br /> NO se la colonna non è di tipo sparse.|  
|IS_COLUMN_SET|String|YES in caso di colonna del set di colonne.<br /><br /> NO se la colonna non fa parte del set di colonne.|  
  
## <a name="users"></a>Utenti  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|uid|Int16|Identificatore utente univoco nel database. 1 corrisponde al proprietario del database.|  
|USER_NAME|Stringa|Il nome utente o il nome del gruppo, univoco nel database.|  
|createdate|DateTime|La data in cui è stato aggiunto l'account.|  
|updatedate|DateTime|Data dell'ultima modifica dell'account.|  
  
## <a name="views"></a>Visualizzazioni  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|Stringa|Catalogo della visualizzazione.|  
|TABLE_SCHEMA|Stringa|Schema contenente la visualizzazione.|  
|TABLE_NAME|Stringa|Nome della visualizzazione.|  
|CHECK_OPTION|Stringa|Tipo di WITH CHECK OPTION. Se la visualizzazione originale è stata creata usando WITH CHECK OPTION, il tipo è CASCADE. In caso contrario, viene restituito NONE.|  
|IS_UPDATABLE|Stringa|Specifica se la visualizzazione può essere aggiornata. Restituisce sempre NO.|  
  
## <a name="viewcolumns"></a>ViewColumns  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|VIEW_CATALOG|Stringa|Catalogo della visualizzazione.|  
|VIEW_SCHEMA|Stringa|Schema contenente la visualizzazione.|  
|VIEW_NAME|Stringa|Nome della visualizzazione.|  
|TABLE_CATALOG|Stringa|Catalogo della tabella associata a questa visualizzazione.|  
|TABLE_SCHEMA|Stringa|Il catalogo della tabella associata a questa visualizzazione.|  
|TABLE_NAME|Stringa|Il nome della tabella associata alla visualizzazione. Tabella di base.|  
|COLUMN_NAME|String|Nome della colonna.|  
  
## <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Nome colonna|Tipo di dati|Descrizione|  
|----------------|--------------|-----------------|  
|assembly_name|String|Nome del file dell'assembly.|  
|udt_name|Stringa|Il nome della classe per l'assembly.|  
|version_major|Oggetto|Il numero di versione principale.|  
|version_minor|Oggetto|Numero di versione secondario.|  
|version_build|Oggetto|Numero di build.|  
|version_revision|Oggetto|Numero di revisione.|  
|culture_info|Object|Informazioni sulle impostazioni cultura associate all'UDT.|  
|public_key|Object|La chiave pubblica usata dall'assembly.|  
|is_fixed_length|Booleano|Specifica se la lunghezza del tipo è sempre uguale a max_length.|  
|max_length|Int16|La lunghezza massima del tipo in byte.|  
|Create_Date|DateTime|La data di creazione o di registrazione dell'assembly.|  
|Permission_set_desc|Stringa|Il nome descrittivo del set di autorizzazioni o del livello di sicurezza dell'assembly.|  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
