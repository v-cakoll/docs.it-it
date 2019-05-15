---
title: Provider di dati .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: 9fead8a5d54fba7232831bba349f27b7eed4657b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583796"
---
# <a name="net-framework-data-providers"></a>Provider di dati .NET Framework
Un provider di dati .NET Framework viene utilizzato per la connessione a un database, l'esecuzione di comandi e il recupero dei risultati. Tali risultati vengono elaborati direttamente, inseriti in un oggetto <xref:System.Data.DataSet> in modo da consentirne l'esposizione all'utente se necessario, combinati con dati provenienti da più origini o elaborati in modalità remota tra livelli. I provider di dati .NET framework sono leggeri, la creazione di un livello minimo tra l'origine dati e codice, migliorando le prestazioni senza compromettere le funzionalità.  
  
 La tabella seguente elenca i provider di dati inclusi in .NET Framework.  
  
|Provider di dati .NET Framework|Descrizione|  
|-------------------------------------------------------------------------------|-----------------|  
|Provider di dati .NET Framework per SQL Server|Consente l'accesso ai dati per Microsoft SQL Server. Usa lo spazio dei nomi <xref:System.Data.SqlClient> .|  
|Provider di dati .NET Framework per OLE DB|Per origini dati esposte tramite OLE DB. Usa lo spazio dei nomi <xref:System.Data.OleDb> .|  
|Provider di dati .NET Framework per ODBC|Per origini dati esposte tramite ODBC. Usa lo spazio dei nomi <xref:System.Data.Odbc> .|  
|Provider di dati .NET Framework per Oracle|Per origini dei dati Oracle. Il Provider di dati .NET Framework per Oracle supporta software client Oracle versione 8.1.7 e versioni successive e utilizza il <xref:System.Data.OracleClient> dello spazio dei nomi.|  
|Provider EntityClient|Fornisce accesso ai dati per le applicazioni Entity Data Model (EDM). Usa lo spazio dei nomi <xref:System.Data.EntityClient> .|  
|Provider di dati .NET framework per SQL Server Compact 4.0.|Fornisce l'accesso ai dati per Microsoft SQL Server Compact 4.0. Usa lo spazio dei nomi [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Oggetti principali dei provider di dati .NET Framework  
 La tabella seguente delinea i quattro oggetti principali che costituiscono un provider di dati .NET Framework.  
  
|Object|Descrizione|  
|------------|-----------------|  
|`Connection`|Consente di stabilire una connessione a un'origine dati specifica. La classe di base per tutti gli oggetti `Connection` è <xref:System.Data.Common.DbConnection> .|  
|`Command`|Consente di eseguire un comando su un'origine dati. Espone `Parameters` e può essere eseguito nell'ambito di `Transaction` da `Connection`. La classe di base per tutti gli oggetti `Command` è <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Consente di leggere un flusso di dati forward-only di sola lettura da un'origine dati. La classe di base per tutti gli oggetti `DataReader` è <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Consente di popolare un `DataSet` e di risolvere gli aggiornamenti con l'origine dati. La classe di base per tutti gli oggetti `DataAdapter` è <xref:System.Data.Common.DbDataAdapter> .|  
  
 Oltre alle classi principali elencate nella tabella precedente in questo documento, un provider di dati .NET Framework contiene anche le classi elencate nella tabella seguente.  
  
|Object|Descrizione|  
|------------|-----------------|  
|`Transaction`|Consente di inserire i comandi in transazioni nell'origine dati. La classe di base per tutti gli oggetti `Transaction` è <xref:System.Data.Common.DbTransaction> . In ADO.NET è anche disponibile il supporto per le transazioni che usano le classi nello spazio dei nomi <xref:System.Transactions> .|  
|`CommandBuilder`|Oggetto helper che genera automaticamente le proprietà dei comandi di un oggetto `DataAdapter` o deriva le informazioni sui parametri da una stored procedure e popola la raccolta `Parameters` di un oggetto `Command` . La classe di base per tutti gli oggetti `CommandBuilder` è <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Oggetto helper che offre un metodo semplice per creare e gestire il contenuto delle stringhe di connessione usate dagli oggetti `Connection` . La classe di base per tutti gli oggetti `ConnectionStringBuilder` è <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Definisce i parametri di input, output e dei valori restituiti per i comandi e le stored procedure. La classe di base per tutti gli oggetti `Parameter` è <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Viene restituito quando si verifica un errore nell'origine dati. Per un errore verificato nel client, i provider di dati .NET Framework generano un'eccezione di .NET Framework. La classe di base per tutti gli oggetti `Exception` è <xref:System.Data.Common.DbException> .|  
|`Error`|Espone le informazioni di un avviso o di un errore restituito da un'origine dati.|  
|`ClientPermission`|Fornito per gli attributi di sicurezza dall'accesso codice provider di dati .NET Framework. La classe di base per tutti gli oggetti `ClientPermission` è <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Provider di dati .NET Framework per SQL Server (SqlClient)  
 Il Provider di dati .NET Framework per SQL Server (SqlClient) usa il proprio protocollo per comunicare con SQL Server. È leggera e offre buone prestazioni perché è ottimizzato per l'accesso a SQL Server direttamente senza l'aggiunta di un livello OLE DB oppure Open Database Connectivity (ODBC). Nella figura seguente mette a confronto il Provider di dati .NET Framework per SQL Server con il Provider di dati .NET Framework per OLE DB. Il Provider di dati .NET Framework per OLE DB comunica a un'origine dati OLE DB tramite il componente servizio OLE DB, che fornisce pool di connessioni e servizi di transazione sia il provider OLE DB per l'origine dati.  
  
> [!NOTE]
>  Il Provider di dati .NET Framework per ODBC è un'architettura simile al Provider di dati .NET Framework per OLE DB. ad esempio, chiama un componente servizio ODBC.  
  
 ![Provider di dati](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Confronto tra il provider di dati .NET Framework per SQL Server e il provider di dati .NET Framework per OLE DB  
  
 Il Provider di dati .NET Framework per SQL Server-classi si trovano nel <xref:System.Data.SqlClient> dello spazio dei nomi.  
  
 Il Provider di dati .NET Framework per SQL Server supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il Provider di dati .NET Framework per SQL Server, per impostazione predefinita, automaticamente viene integrato in una transazione e ottiene i dettagli di transazione da Servizi componenti di Windows o <xref:System.Transactions>. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.SqlClient` nelle applicazioni.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Provider di dati .NET Framework per OLE DB  
 Il Provider di dati .NET Framework per OLE DB (OleDb) Usa OLE DB nativo tramite l'interoperabilità COM per abilitare l'accesso ai dati. Il Provider di dati .NET Framework per OLE DB supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il Provider di dati .NET Framework per OLE DB, per impostazione predefinita, automaticamente viene integrato in una transazione e ottiene i dettagli di transazione da Servizi componenti di Windows. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nella tabella seguente sono elencati i provider che sono stati testati con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Driver|Provider|  
|------------|--------------|  
|SQLOLEDB|Provider Microsoft OLE DB per SQL Server|  
|MSDAORA|Provider Microsoft OLE DB per Oracle|  
|Microsoft.Jet.OLEDB.4.0|Provider OLE DB per Microsoft Jet|  
  
> [!NOTE]
>  È sconsigliato l'uso di un database Access (Jet) come origine dati per applicazioni con multithreading, quali le applicazioni [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Se è necessario usare Jet come origine dati per un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , tenere presente che le applicazioni [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] che si connettono a un database Access possono riscontrare problemi di connessione.  
  
 Il Provider di dati .NET Framework per OLE DB non supporta le interfacce OLE DB versione 2.5. Provider OLE DB che richiedono il supporto per le interfacce OLE DB 2.5 non funzionerà correttamente con il Provider di dati .NET Framework per OLE DB. Tra tali provider sono inclusi il provider Microsoft OLE DB per Exchange e il provider Microsoft OLE DB per Internet Publishing.  
  
 Il Provider di dati .NET Framework per OLE DB non funziona con il provider OLE DB per ODBC (MSDASQL). Per accedere a un'origine dati ODBC utilizzando [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], utilizzare il Provider di dati .NET Framework per ODBC.  
  
 Provider di dati .NET framework per OLE DB classi si trovano nel <xref:System.Data.OleDb> dello spazio dei nomi. Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.OleDb` nelle applicazioni.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 Il Provider di dati .NET Framework per ODBC (Odbc) usa il Manager di Driver ODBC (DM) nativa per abilitare l'accesso ai dati. Il provider di dati ODBC supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il provider di dati per ODBC si inserisce automaticamente, per impostazione predefinita, in una transazione e ottiene i dettagli relativi alla transazione da Servizi componenti di Windows. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nella tabella seguente sono elencati i driver ODBC testati con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Driver|  
|------------|  
|SQL Server|  
|Microsoft ODBC per Oracle|  
|Driver per Microsoft Access (*.mdb)|  
  
 Provider di dati .NET framework per le classi ODBC si trovano nel <xref:System.Data.Odbc> dello spazio dei nomi.  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.Odbc` nelle applicazioni.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  Il Provider di dati .NET Framework per ODBC è richiesto MDAC 2.6 o versione successiva e si consiglia MDAC 2.8 SP1. È possibile scaricare MDAC 2.8 SP1 da [Archiviazione e accesso ai dati: Centro per sviluppatori](https://go.microsoft.com/fwlink/?linkid=4173).  
  
## <a name="net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 Il Provider di dati .NET Framework per Oracle (OracleClient) consente l'accesso alle origini dati Oracle tramite software di connettività client Oracle. Il provider di dati può essere usato con il software client Oracle 8.1.7 o versione successiva. Il provider di dati supporta transazioni sia locali che distribuite. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Il Provider di dati .NET Framework per Oracle richiede il software client Oracle (versione 8.1.7 o versione successiva) nel sistema prima di connettersi a un'origine dati Oracle.  
  
 Provider di dati .NET framework per le classi di Oracle si trovano nel <xref:System.Data.OracleClient> dello spazio dei nomi sono contenute nel `System.Data.OracleClient.dll` assembly. Quando si compila un'applicazione in cui viene usato il provider di dati, è necessario fare riferimento sia a `System.Data.dll` che a `System.Data.OracleClient.dll` .  
  
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
 A seconda dell'origine dati e progettazione per l'applicazione, la scelta di provider di dati .NET Framework può migliorare le prestazioni, funzionalità e l'integrità dell'applicazione. Nella tabella seguente illustra i vantaggi e limitazioni di ogni provider di dati .NET Framework.  
  
|Provider|Note|  
|--------------|-----------|  
|Provider di dati .NET Framework per SQL Server|Consigliato per le applicazioni di livello intermedio che utilizzano Microsoft SQL Server.<br /><br /> Consigliato per applicazioni a un solo livello che utilizzano Microsoft Database Engine (MSDE) o SQL Server.<br /><br /> Consigliato rispetto all'uso del provider OLE DB per SQL Server (SQLOLEDB) con il Provider di dati .NET Framework per OLE DB.|  
|Provider di dati .NET Framework per OLE DB|Per SQL Server, il Provider di dati .NET Framework per SQL Server è consigliabile invece di questo provider.<br /><br /> Consigliato per applicazioni a un solo livello che usano database di Microsoft Access. L'uso di un database di Microsoft Access per applicazioni di livello intermedio non è consigliato.|  
|Provider di dati .NET Framework per ODBC|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati ODBC.|  
|Provider di dati .NET Framework per Oracle|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati Oracle.|  
  
## <a name="entityclient-provider"></a>Provider EntityClient  
 Il provider EntityClient è usato per l'accesso ai dati basati su Entity Data Model (EDM). A differenza degli altri provider di dati .NET Framework, non interagisce direttamente con un'origine dati, ma usa Entity SQL per comunicare con il provider di dati sottostante. Per altre informazioni, vedere [EntityClient Provider per Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
