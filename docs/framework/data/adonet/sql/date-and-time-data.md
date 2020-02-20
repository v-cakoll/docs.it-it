---
title: Dati relativi a data e ora
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: bdcbaffe1be4933b89c7bf0d3a11e1bb871bc2bd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450298"
---
# <a name="date-and-time-data"></a>Dati relativi a data e ora
In SQL Server 2008 vengono introdotti nuovi tipi di dati per la gestione di informazioni relative a data e ora. I nuovi tipi di dati includono tipi separati per data e ora e tipi di dati espansi che offrono miglioramenti in termini di intervallo, precisione e gestione del fuso orario. A partire da .NET Framework versione 3.5 Service Pack 1 (SP1), il provider di dati .NET Framework per SQL Server (<xref:System.Data.SqlClient>) fornisce supporto completo per tutte le nuove funzionalità del Motore di database di SQL Server 2008. Per usare queste nuove funzionalità con SqlClient, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).  
  
 Nelle versioni di SQL Server precedenti a SQL Server 2008 erano disponibili solo due tipi di dati per l'uso di valori di data e ora: `datetime` e `smalldatetime`. Poiché entrambi questi tipi di dati contengono sia il valore della data che il valore dell'ora, risulta difficile usare uno solo dei due valori. Questi tipi di dati supportano inoltre solo le date che ricorrono dopo l'introduzione del calendario gregoriano in Inghilterra, nel 1753. Un altro limite è inoltre costituito dal fatto che i tipi di dati precedenti non dipendono dal fuso orario, pertanto è difficile usare dati provenienti da fusi orari diversi.  
  
 Nella documentazione online di SQL Server sono disponibili informazioni complete relative ai tipi di dati di SQL Server. Nella tabella seguente sono elencati gli argomenti di base specifici della versione per i dati relativi a data e ora.  
  
 **Documentazione di SQL Server**  
  
1. [Uso di dati relativi a data e ora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a>Tipi di dati relativi a data e ora introdotti in SQL Server 2008  
 La tabella seguente descrive i nuovi tipi di dati relativi a data e ora.  
  
|Tipo di dati SQL Server|Descrizione|  
|--------------------------|-----------------|  
|`date`|Il tipo di dati `date` include un intervallo compreso tra l'1 gennaio 01 e il 31 dicembre 9999 con un'accuratezza di 1 giorno. Il valore predefinito è 1 gennaio 1900. Le dimensioni di archiviazione sono di 3 byte.|  
|`time`|Il tipo di dati `time` consente di archiviare solo i valori relativi all'ora, in base a un formato a 24 ore. Il tipo di dati `time` include un intervallo compreso tra 00.00.00.0000000 e 23.59.59.9999999 con un'accuratezza di 100 nanosecondi. Il valore predefinito è 00.00.00.0000000 (mezzanotte). Il tipo di dati `time` supporta la precisione in secondi frazionari definita dall'utente e le dimensioni di archiviazione variano da 3 a 6 byte, in base alla precisione specificata.|  
|`datetime2`|Il tipo di dati `datetime2` combina l'intervallo e la precisione dei tipi di dati `date` e `time` in un unico tipo di dati.<br /><br /> I valori predefiniti e i formati dei valori letterali stringa sono identici a quelli definiti nei tipi di dati `date` e `time`.|  
|`datetimeoffset`|Il tipo di dati `datetimeoffset` offre tutte le funzionalità di `datetime2`, con l'aggiunta di un offset di fusi orari. L'offset di fusi orari è rappresentato come [+&#124;-] HH:MM. HH è un numero a 2 cifre compreso tra 00 e 14 che rappresenta il numero di ore nell'offset di fusi orari. MM è un numero a 2 cifre compreso tra 00 e 59 che rappresenta il numero di minuti aggiuntivi nell'offset di fusi orari. I formati di ora sono supportati fino a 100 nanosecondi. Il segno + o - obbligatorio indica se l'offset di fusi orari deve essere aggiunto o sottratto dall'ora UTC (Universal Time Coordinate o ora di Greenwich) per ottenere l'ora locale.|  
  
> [!NOTE]
> Per altre informazioni sull'uso della parola chiave `Type System Version`, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="date-format-and-date-order"></a>Formato e ordine della data  
 La modalità di analisi dei valori di data e ora in SQL Server dipende non solo dalla versione del sistema di tipi e del server, ma anche dalle impostazioni di formato e lingua predefinite per il server. È possibile che una stringa di data corretta in base ai formati supportati per una determinata lingua non sia riconosciuta se la query viene eseguita in una connessione con impostazioni diverse del formato di lingua e data.  
  
 L'istruzione Transact-SQL SET LANGUAGE consente di impostare in modo implicito il valore di DATEFORMAT che determina l'ordine delle parti relative alla data. È possibile usare l'istruzione Transact-SQL SET DATEFORMAT in una connessione per evitare ambiguità tra i valori di data ordinando le parti relative alla data in base all'ordine MDY, DMY, YMD, YDM, MYD o DYM.  
  
 Se non si specifica alcun valore di DATEFORMAT per la connessione, in SQL Server viene usata la lingua predefinita associata alla connessione. Una stringa '01/02/03' relativa alla data verrebbe ad esempio interpretata come MDY (2 gennaio 2003) in un server con la lingua impostata su Inglese (Stati Uniti) e come DMY (1 febbraio 2003) in un server con la lingua impostata su Inglese (Regno Unito). L'anno viene determinato tramite la regola per l'anno di cambio data di SQL Server, che definisce la data che determina il cambio per l'assegnazione del valore del secolo. Per altre informazioni, vedere [opzione two digit year cutoff](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).  
  
> [!NOTE]
> Il formato della data YDM non è supportato in caso di conversione da un formato stringa a `date`, `time`, `datetime2` o `datetimeoffset`.  
  
 Per ulteriori informazioni sul modo in cui SQL Server interpreta i dati di data e ora, vedere [utilizzo di dati di data e ora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).  
  
## <a name="datetime-data-types-and-parameters"></a>Tipi di dati e parametri relativi a data e ora  
 Le enumerazioni seguenti sono state aggiunte a <xref:System.Data.SqlDbType> per supportare i nuovi tipi di dati relativi a data e ora.  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

È possibile specificare il tipo di dati di un oggetto <xref:System.Data.SqlClient.SqlParameter> usando una delle enumerazioni <xref:System.Data.SqlDbType> precedenti. 

> [!NOTE]
> Non è possibile impostare la proprietà `DbType` di un `SqlParameter` `SqlDbType.Date`.

 È inoltre possibile specificare il tipo di un oggetto <xref:System.Data.SqlClient.SqlParameter> in modo generico impostando la proprietà <xref:System.Data.SqlClient.SqlParameter.DbType%2A> di un oggetto `SqlParameter` su un particolare valore dell'enumerazione <xref:System.Data.DbType>. I seguenti valori di enumerazione sono stati aggiunti a <xref:System.Data.DbType> per supportare i tipi di dati `datetime2` e `datetimeoffset`:  
  
- DbType.DateTime2  
  
- DbType.DateTimeOffset  
  
 Queste nuove enumerazioni integrano le enumerazioni `Date`, `Time` e `DateTime`, che erano presenti nelle versioni precedenti di .NET Framework.  
  
 Il tipo di un oggetto parametro del provider di dati .NET Framework viene dedotto dal tipo del valore dell'oggetto parametro .NET Framework o dal valore `DbType` dell'oggetto parametro. Non sono stati introdotti nuovi tipi di dati <xref:System.Data.SqlTypes> per supportare i nuovi tipi di dati relativi a data e ora. La tabella seguente descrive i mapping tra i tipi di dati relativi a data e ora di SQL Server 2008 e i tipi di dati CLR.  
  
|Tipo di dati SQL Server|Tipo .NET Framework|System.Data.SqlDbType|System.Data.DbType|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|date|System.DateTime|Data|Data|  
|time|System.TimeSpan|Tempo|Tempo|  
|datetime2|System.DateTime|DateTime2|DateTime2|  
|datetimeoffset|System.DateTimeOffset|DateTimeOffset|DateTimeOffset|  
|datetime|System.DateTime|DateTime|DateTime|  
|smalldatetime|System.DateTime|DateTime|DateTime|  
  
### <a name="sqlparameter-properties"></a>Proprietà di SqlParameter  
 La tabella seguente descrive le proprietà di `SqlParameter` che riguardano i tipi di dati relativi a data e ora.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|Ottiene o imposta un valore che indica se un valore ammette i valori null. Quando si invia un valore di parametro null al server, è necessario specificare <xref:System.DBNull> invece di `null` (`Nothing` in Visual Basic). Per altre informazioni sui valori null di database, vedere [Handling Null Values](handling-null-values.md).|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|Ottiene o imposta il numero massimo di cifre usato per rappresentare il valore. Questa impostazione viene ignorata per i tipi di dati relativi a data e ora.|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|Ottiene o imposta il numero di posizioni decimali in cui viene risolta la parte del valore relativa all'ora per `Time`, `DateTime2` e `DateTimeOffset`. Il valore predefinito è 0, che indica che la scala effettiva viene dedotta dal valore e inviata al server.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Proprietà ignorata per i tipi di dati relativi a data e ora.|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Ottiene o imposta il valore del parametro.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Ottiene o imposta il valore del parametro.|  
  
> [!NOTE]
> I valori relativi all'ora minori di zero o maggiori o uguali a 24 ore generano un evento <xref:System.ArgumentException>.  
  
### <a name="creating-parameters"></a>Creazione di parametri  
 È possibile creare un oggetto <xref:System.Data.SqlClient.SqlParameter> usando il relativo costruttore o aggiungendolo a una raccolta <xref:System.Data.SqlClient.SqlCommand> di <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> chiamando il metodo `Add` di <xref:System.Data.SqlClient.SqlParameterCollection>. Il metodo `Add` accetta come input argomenti del costruttore o un oggetto parametro esistente.  
  
 Nelle sezioni successive di questo argomento vengono forniti esempi di come specificare i parametri relativi a data e ora. Per ulteriori esempi di utilizzo dei parametri, vedere [configurazione di parametri e tipi di dati dei](../configuring-parameters-and-parameter-data-types.md) parametri e [parametri DataAdapter](../dataadapter-parameters.md).  
  
### <a name="date-example"></a>Esempio relativo a Date  
 Nel frammento di codice seguente viene illustrato come specificare un parametro `date`.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a>Esempio relativo a Time  
 Nel frammento di codice seguente viene illustrato come specificare un parametro `time`.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a>Esempio relativo a DateTime2  
 Nel frammento di codice seguente viene illustrato come specificare un parametro `datetime2` con entrambe le parti relative a data e ora.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a>Esempio relativo a DateTimeOffset  
 Nel frammento di codice seguente viene illustrato come specificare un parametro `DateTimeOffSet` con le parti relative a data e ora e un offset di fusi orari pari a 0.  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a>AddWithValue  
 È anche possibile fornire i parametri usando il metodo `AddWithValue` di un oggetto <xref:System.Data.SqlClient.SqlCommand>, come illustrato nel frammento di codice seguente. Il metodo `AddWithValue` non consente tuttavia di specificare <xref:System.Data.SqlClient.SqlParameter.DbType%2A> o <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> per il parametro.  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 È possibile eseguire il mapping del parametro `@date` a un tipo di dati `date`, `datetime` o `datetime2` nel server. Quando si usano i nuovi tipi di dati `datetime`, è necessario impostare in modo esplicito la proprietà <xref:System.Data.SqlDbType> del parametro sul tipo di dati dell'istanza. Se si usa <xref:System.Data.SqlDbType.Variant> o si forniscono in modo implicito i valori del parametro, possono verificarsi problemi di compatibilità con le versioni precedenti per quanto riguarda i tipi di dati `datetime` e `smalldatetime`.  
  
 La tabella seguente indica i tipi `SqlDbTypes` dedotti dai diversi tipi CLR:  
  
|Tipo CLR|Tipo SqlDbType dedotto|  
|--------------|------------------------|  
|DateTime|SqlDbType.DateTime|  
|TimeSpan|SqlDbType.Time|  
|DateTimeOffset|SqlDbType.DateTimeOffset|  
  
## <a name="retrieving-date-and-time-data"></a>Recupero di dati relativi a data e ora  
 La tabella seguente descrive i metodi usati per recuperare i valori di data e ora di SQL Server 2008.  
  
|Metodo SqlClient|Descrizione|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|Recupera il valore della colonna specificata come struttura <xref:System.DateTime>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|Recupera il valore della colonna specificata come struttura <xref:System.DateTimeOffset>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|Restituisce il tipo che corrisponde al tipo sottostante specifico del provider per il campo. Restituisce gli stessi tipi di `GetFieldType` per i nuovi tipi di data e ora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|Recupera il valore della colonna specificata. Restituisce gli stessi tipi di `GetValue` per i nuovi tipi di data e ora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|Recupera i valori nella matrice specificata.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|Recupera il valore della colonna come <xref:System.Data.SqlTypes.SqlString>. Se i dati non possono essere espressi come <xref:System.InvalidCastException>, viene generata un'eccezione `SqlString`.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|Recupera i dati della colonna come oggetto `SqlDbType` predefinito. Restituisce gli stessi tipi di `GetValue` per i nuovi tipi di data e ora.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|Recupera i valori nella matrice specificata.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|Recupera il valore della colonna come stringa se Type System Version è impostata su SQL Server 2005. Se i dati non possono essere espressi come stringa, viene generata un'eccezione <xref:System.InvalidCastException>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|Recupera il valore della colonna specificata come struttura <xref:System.TimeSpan>.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|Recupera il valore della colonna specificata come tipo CLR sottostante.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|Recupera i valori della colonna in una matrice.|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|Restituisce un oggetto <xref:System.Data.DataTable> che descrive i metadati del set di risultati.|  
  
> [!NOTE]
> I nuovi tipi `SqlDbTypes` di data e ora non sono supportati per il codice in esecuzione in-process in SQL Server. Se uno di questi tipi viene passato al server, viene generata un'eccezione.  
  
## <a name="specifying-date-and-time-values-as-literals"></a>Impostazione di valori di data e ora come valori letterali  
 È possibile specificare i tipi di dati relativi a data e ora usando formati di stringhe letterali diversi, che vengono quindi valutati da SQL Server in fase di esecuzione e convertiti in strutture di data e ora interne. In SQL Server vengono riconosciuti i dati relativi a data e ora racchiusi tra virgolette singole ('). Negli esempi seguenti vengono illustrati alcuni formati:  
  
- Formati di data alfabetici, ad esempio `'October 15, 2006'`.  
  
- Formati di data numerici, ad esempio `'10/15/2006'`.  
  
- Formati di stringa non separati, ad esempio `'20061015'`, che verrebbe interpretato come 15 ottobre 2006 se si usa il formato di data standard ISO.  
  
> [!NOTE]
> Nella documentazione online di SQL Server sono disponibili informazioni complete su tutti i formati di stringhe letterali e le altre funzionalità dei tipi di dati relativi a data e ora.  
  
 I valori relativi all'ora minori di zero o maggiori o uguali a 24 ore generano un evento <xref:System.ArgumentException>.  
  
## <a name="resources-in-sql-server-books-online"></a>Risorse nella documentazione online di SQL Server  
 Per ulteriori informazioni sull'utilizzo dei valori di data e ora in SQL Server, vedere le risorse seguenti nella documentazione online di SQL Server.  
  
|Argomento|Descrizione|  
|-----------|-----------------|  
|[Funzioni e tipi di dati di data e ora (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|Viene fornita una panoramica di tutti i tipi di dati e le funzioni relativi a data e ora di Transact-SQL.|  
|[Uso di dati relativi a data e ora](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))|Fornisce informazioni sulle funzioni e sui tipi di dati relativi a data e ora ed esempi del loro uso.|  
|[Tipi di dati (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql)|Descrive i tipi di dati di sistema in SQL Server.|  
  
## <a name="see-also"></a>Vedere anche

- [Mapping dei tipi di dati SQL Server](../sql-server-data-type-mappings.md)
- [Configurazione di parametri e tipi di dati dei parametri](../configuring-parameters-and-parameter-data-types.md)
- [Tipi di dati SQL Server e ADO.NET](sql-server-data-types.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
