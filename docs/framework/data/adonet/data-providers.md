---
title: Provider di dati .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 2c986aab33f2c4dcefb5924ea61e8b9f6b3c50a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347806"
---
# <a name="net-framework-data-providers"></a>Provider di dati .NET Framework
Un provider di dati .NET Framework viene utilizzato per la connessione a un database, l'esecuzione di comandi e il recupero dei risultati. Tali risultati vengono elaborati direttamente, inseriti in un oggetto <xref:System.Data.DataSet> in modo da consentirne l'esposizione all'utente se necessario, combinati con dati provenienti da più origini o elaborati in modalità remota tra livelli. I provider di dati .NET Framework sono semplici, creando un livello minimo tra l'origine dati e il codice, aumentando le prestazioni senza sacrificare le funzionalità.  
  
 Nella tabella seguente sono elencati i provider di dati inclusi nel .NET Framework.  
  
|Provider di dati .NET Framework|Descrizione|  
|-------------------------------------------------------------------------------|-----------------|  
|Provider di dati .NET Framework per SQL Server|Consente l'accesso ai dati per Microsoft SQL Server. Usa lo spazio dei nomi <xref:System.Data.SqlClient> .|  
|Provider di dati .NET Framework per OLE DB|Per origini dati esposte tramite OLE DB. Usa lo spazio dei nomi <xref:System.Data.OleDb> .|  
|Provider di dati .NET Framework per ODBC|Per origini dati esposte tramite ODBC. Usa lo spazio dei nomi <xref:System.Data.Odbc> .|  
|Provider di dati .NET Framework per Oracle|Per origini dei dati Oracle. Il .NET Framework provider di dati per Oracle supporta la versione del software client Oracle 8.1.7 e versioni successive e usa lo spazio dei nomi <xref:System.Data.OracleClient>.|  
|Provider EntityClient|Fornisce accesso ai dati per le applicazioni Entity Data Model (EDM). Usa lo spazio dei nomi <xref:System.Data.EntityClient> .|  
|.NET Framework provider di dati per SQL Server Compact 4,0.|Fornisce l'accesso ai dati per Microsoft SQL Server Compact 4,0. Usa lo spazio dei nomi [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Oggetti principali dei provider di dati .NET Framework  
 La tabella seguente illustra i quattro oggetti principali che costituiscono un provider di dati .NET Framework.  
  
|Oggetto di|Descrizione|  
|------------|-----------------|  
|`Connection`|Consente di stabilire una connessione a un'origine dati specifica. La classe di base per tutti gli oggetti `Connection` è <xref:System.Data.Common.DbConnection> .|  
|`Command`|Consente di eseguire un comando su un'origine dati. Espone `Parameters` e può essere eseguito nell'ambito di `Transaction` da `Connection`. La classe di base per tutti gli oggetti `Command` è <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Consente di leggere un flusso di dati forward-only di sola lettura da un'origine dati. La classe di base per tutti gli oggetti `DataReader` è <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Consente di popolare un `DataSet` e di risolvere gli aggiornamenti con l'origine dati. La classe di base per tutti gli oggetti `DataAdapter` è <xref:System.Data.Common.DbDataAdapter> .|  
  
 Oltre alle classi principali elencate nella tabella riportata in precedenza in questo documento, un provider di dati .NET Framework contiene anche le classi elencate nella tabella seguente.  
  
|Oggetto di|Descrizione|  
|------------|-----------------|  
|`Transaction`|Consente di inserire i comandi in transazioni nell'origine dati. La classe di base per tutti gli oggetti `Transaction` è <xref:System.Data.Common.DbTransaction> . In ADO.NET è anche disponibile il supporto per le transazioni che usano le classi nello spazio dei nomi <xref:System.Transactions> .|  
|`CommandBuilder`|Oggetto helper che genera automaticamente le proprietà dei comandi di un oggetto `DataAdapter` o deriva le informazioni sui parametri da una stored procedure e popola la raccolta `Parameters` di un oggetto `Command` . La classe di base per tutti gli oggetti `CommandBuilder` è <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Oggetto helper che offre un metodo semplice per creare e gestire il contenuto delle stringhe di connessione usate dagli oggetti `Connection` . La classe di base per tutti gli oggetti `ConnectionStringBuilder` è <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Definisce i parametri di input, output e dei valori restituiti per i comandi e le stored procedure. La classe di base per tutti gli oggetti `Parameter` è <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Viene restituito quando si verifica un errore nell'origine dati. Per un errore verificatosi nel client, i provider di dati .NET Framework generano un'eccezione .NET Framework. La classe di base per tutti gli oggetti `Exception` è <xref:System.Data.Common.DbException> .|  
|`Error`|Espone le informazioni di un avviso o di un errore restituito da un'origine dati.|  
|`ClientPermission`|Fornito per .NET Framework attributi di sicurezza per l'accesso al codice del provider di dati. La classe di base per tutti gli oggetti `ClientPermission` è <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Provider di dati .NET Framework per SQL Server (SqlClient)  
 Il provider di dati .NET Framework per SQL Server (SqlClient) usa il proprio protocollo per comunicare con SQL Server. Si tratta di un metodo leggero ed è ottimizzato per l'accesso a un SQL Server direttamente senza aggiungere un livello OLE DB o Open Database Connectivity (ODBC). Nell'illustrazione seguente viene contrapposto il provider di dati .NET Framework per SQL Server con il provider di dati .NET Framework per OLE DB. Il .NET Framework provider di dati per OLE DB comunica con un'origine dati OLE DB tramite il componente del servizio OLE DB, che fornisce pool di connessioni e servizi di transazione, e il provider OLE DB per l'origine dati.  
  
> [!NOTE]
> Il .NET Framework provider di dati per ODBC presenta un'architettura simile a quella della .NET Framework provider di dati per OLE DB; ad esempio, effettua una chiamata a un componente del servizio ODBC.  
  
 ![Provider di dati](./media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Confronto tra il provider di dati .NET Framework per SQL Server e il provider di dati .NET Framework per OLE DB  
  
 Il .NET Framework provider di dati per le classi SQL Server si trova nello spazio dei nomi <xref:System.Data.SqlClient>.  
  
 Il provider di dati .NET Framework per SQL Server supporta transazioni sia locali che distribuite. Per le transazioni distribuite, la .NET Framework provider di dati per SQL Server, per impostazione predefinita, viene integrata automaticamente in una transazione e ottiene i dettagli della transazione da Servizi componenti di Windows o <xref:System.Transactions>. Per ulteriori informazioni, vedere [transazioni e concorrenza](transactions-and-concurrency.md).  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.SqlClient` nelle applicazioni.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Provider di dati .NET Framework per OLE DB  
 Il provider di dati .NET Framework per OLE DB (OleDb) USA OLE DB nativi tramite l'interoperabilità COM per consentire l'accesso ai dati. Il provider di dati .NET Framework per OLE DB supporta transazioni sia locali che distribuite. Per le transazioni distribuite, la .NET Framework provider di dati per OLE DB, per impostazione predefinita, viene integrata automaticamente in una transazione e ottiene i dettagli della transazione da Servizi componenti di Windows. Per ulteriori informazioni, vedere [transazioni e concorrenza](transactions-and-concurrency.md).  
  
 La tabella seguente illustra i provider testati con ADO.NET.  
  
|Driver|Provider|  
|------------|--------------|  
|SQLOLEDB|Provider di OLE DB Microsoft per SQL Server|  
|MSDAORA|Provider Microsoft OLE DB per Oracle|  
|Microsoft.Jet.OLEDB.4.0|Provider OLE DB per Microsoft Jet|  
  
> [!NOTE]
> Non è consigliabile usare un database di Access (Jet) come origine dati per le applicazioni multithreading, ad esempio le applicazioni ASP.NET. Se è necessario usare Jet come origine dati per un'applicazione ASP.NET, tenere presente che le applicazioni ASP.NET che si connettono a un database di Access possono riscontrare problemi di connessione.  
  
 Il provider di dati .NET Framework per OLE DB non supporta le interfacce OLE DB versione 2,5. OLE DB provider che richiedono il supporto per le interfacce OLE DB 2,5 non funzioneranno correttamente con il .NET Framework provider di dati per OLE DB. Tra tali provider sono inclusi il provider Microsoft OLE DB per Exchange e il provider Microsoft OLE DB per Internet Publishing.  
  
 Il .NET Framework provider di dati per OLE DB non funziona con il provider di OLE DB per ODBC (MSDASQL). Per accedere a un'origine dati ODBC utilizzando ADO.NET, utilizzare l'provider di dati .NET Framework per ODBC.  
  
 .NET Framework provider di dati per le classi OLE DB si trovano nello spazio dei nomi <xref:System.Data.OleDb>. Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.OleDb` nelle applicazioni.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 Il .NET Framework provider di dati per ODBC (ODBC) USA Gestione driver ODBC nativa (DM) per abilitare l'accesso ai dati. Il provider di dati ODBC supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il provider di dati per ODBC si inserisce automaticamente, per impostazione predefinita, in una transazione e ottiene i dettagli relativi alla transazione da Servizi componenti di Windows. Per ulteriori informazioni, vedere [transazioni e concorrenza](transactions-and-concurrency.md).  
  
 Nella tabella seguente sono illustrati i driver ODBC testati con ADO.NET.  
  
|Driver|  
|------------|  
|SQL Server|  
|Microsoft ODBC per Oracle|  
|Driver per Microsoft Access (*.mdb)|  
  
 .NET Framework provider di dati per le classi ODBC si trovano nello spazio dei nomi <xref:System.Data.Odbc>.  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.Odbc` nelle applicazioni.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
> Per la .NET Framework provider di dati per ODBC è necessario MDAC 2,6 o versione successiva ed è consigliato MDAC 2,8 SP1. È possibile scaricare MDAC 2,8 SP1 dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=5793).
  
## <a name="net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 Il .NET Framework provider di dati per Oracle (OracleClient) consente l'accesso ai dati alle origini dati Oracle tramite il software di connettività client Oracle. Il provider di dati può essere usato con il software client Oracle 8.1.7 o versione successiva. Il provider di dati supporta transazioni sia locali che distribuite. Per ulteriori informazioni, vedere [transazioni e concorrenza](transactions-and-concurrency.md).  
  
 Il .NET Framework provider di dati per Oracle richiede il software client Oracle (versione 8.1.7 o successiva) nel sistema prima di potersi connettere a un'origine dati Oracle.  
  
 .NET Framework provider di dati per le classi Oracle si trovano nello spazio dei nomi <xref:System.Data.OracleClient> e sono contenuti nell'assembly `System.Data.OracleClient.dll`. Quando si compila un'applicazione in cui viene usato il provider di dati, è necessario fare riferimento sia a `System.Data.dll` che a `System.Data.OracleClient.dll` .  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.OracleClient` nelle applicazioni.  
  
```vb  
Imports System.Data  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data;  
using System.Data.OracleClient;  
```  
  
## <a name="choosing-a-net-framework-data-provider"></a>Scelta di un provider di dati .NET Framework  
 A seconda della progettazione e dell'origine dati per l'applicazione, la scelta del provider di dati .NET Framework può migliorare le prestazioni, la funzionalità e l'integrità dell'applicazione. Nella tabella seguente vengono illustrati i vantaggi e le limitazioni di ogni provider di dati .NET Framework.  
  
|Provider|Note|  
|--------------|-----------|  
|Provider di dati .NET Framework per SQL Server|Consigliato per applicazioni di livello intermedio che usano Microsoft SQL Server.<br /><br /> Consigliato per applicazioni a un solo livello che usano Microsoft motore di database (MSDE) o SQL Server.<br /><br /> Consigliato rispetto all'uso del provider OLE DB per SQL Server (SQLOLEDB) con il .NET Framework provider di dati per OLE DB.|  
|Provider di dati .NET Framework per OLE DB|Per SQL Server è consigliabile usare il provider di dati .NET Framework per SQL Server anziché questo provider.<br /><br /> Consigliato per applicazioni a un solo livello che usano database di Microsoft Access. L'uso di un database di Microsoft Access per applicazioni di livello intermedio non è consigliato.|  
|Provider di dati .NET Framework per ODBC|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati ODBC.|  
|Provider di dati .NET Framework per Oracle|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati Oracle.|  
  
## <a name="entityclient-provider"></a>Provider EntityClient  
 Il provider EntityClient è usato per l'accesso ai dati basati su Entity Data Model (EDM). A differenza degli altri provider di dati .NET Framework, non interagisce direttamente con un'origine dati, ma usa Entity SQL per comunicare con il provider di dati sottostante. Per ulteriori informazioni, vedere [Provider EntityClient per Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
