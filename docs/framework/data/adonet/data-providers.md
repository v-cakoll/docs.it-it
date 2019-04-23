---
title: Provider di dati .NET Framework
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 03a9fc62-2d24-491a-9fe6-d6bdb6dcb131
ms.openlocfilehash: f821088375bf1df01e75de5e0c226334baca113f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074027"
---
# <a name="net-framework-data-providers"></a>Provider di dati .NET Framework
Un provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] consente di effettuare una connessione a un database, eseguire comandi e recuperare risultati. Tali risultati vengono elaborati direttamente, inseriti in un oggetto <xref:System.Data.DataSet> in modo da consentirne l'esposizione all'utente se necessario, combinati con dati provenienti da più origini o elaborati in modalità remota tra livelli. I provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] presentano una struttura semplice e creano un livello minimo tra l'origine dati e il codice, migliorando quindi le prestazioni senza compromettere le funzionalità.  
  
 La tabella seguente elenca i provider di dati inclusi in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
|Provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] |Descrizione|  
|-------------------------------------------------------------------------------|-----------------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server|Consente l'accesso ai dati per Microsoft SQL Server. Usa lo spazio dei nomi <xref:System.Data.SqlClient> .|  
|Provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB|Per origini dati esposte tramite OLE DB. Usa lo spazio dei nomi <xref:System.Data.OleDb> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per ODBC|Per origini dati esposte tramite ODBC. Usa lo spazio dei nomi <xref:System.Data.Odbc> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per Oracle|Per origini dei dati Oracle. Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle può essere usato con software client Oracle 8.1.7 e versioni successive e usa lo spazio dei nomi <xref:System.Data.OracleClient> .|  
|Provider EntityClient|Fornisce accesso ai dati per le applicazioni Entity Data Model (EDM). Usa lo spazio dei nomi <xref:System.Data.EntityClient> .|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server Compact 4.0.|Fornisce l'accesso ai dati per Microsoft SQL Server Compact 4.0. Usa lo spazio dei nomi [System.Data.SqlServerCe](https://docs.microsoft.com/previous-versions/sql/compact/sql-server-compact-4.0/ec4st0e3(v=vs.100)) .|  
  
## <a name="core-objects-of-net-framework-data-providers"></a>Oggetti principali dei provider di dati .NET Framework  
 La tabella seguente delinea i quattro oggetti principali che costituiscono un provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  
  
|Object|Descrizione|  
|------------|-----------------|  
|`Connection`|Consente di stabilire una connessione a un'origine dati specifica. La classe di base per tutti gli oggetti `Connection` è <xref:System.Data.Common.DbConnection> .|  
|`Command`|Consente di eseguire un comando su un'origine dati. Espone `Parameters` e può essere eseguito nell'ambito di `Transaction` da `Connection`. La classe di base per tutti gli oggetti `Command` è <xref:System.Data.Common.DbCommand> .|  
|`DataReader`|Consente di leggere un flusso di dati forward-only di sola lettura da un'origine dati. La classe di base per tutti gli oggetti `DataReader` è <xref:System.Data.Common.DbDataReader> .|  
|`DataAdapter`|Consente di popolare un `DataSet` e di risolvere gli aggiornamenti con l'origine dati. La classe di base per tutti gli oggetti `DataAdapter` è <xref:System.Data.Common.DbDataAdapter> .|  
  
 Oltre alle classi principali elencate nella tabella precedente, un provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] contiene anche le classi elencate nella tabella seguente.  
  
|Object|Descrizione|  
|------------|-----------------|  
|`Transaction`|Consente di inserire i comandi in transazioni nell'origine dati. La classe di base per tutti gli oggetti `Transaction` è <xref:System.Data.Common.DbTransaction> . In ADO.NET è anche disponibile il supporto per le transazioni che usano le classi nello spazio dei nomi <xref:System.Transactions> .|  
|`CommandBuilder`|Oggetto helper che genera automaticamente le proprietà dei comandi di un oggetto `DataAdapter` o deriva le informazioni sui parametri da una stored procedure e popola la raccolta `Parameters` di un oggetto `Command` . La classe di base per tutti gli oggetti `CommandBuilder` è <xref:System.Data.Common.DbCommandBuilder> .|  
|`ConnectionStringBuilder`|Oggetto helper che offre un metodo semplice per creare e gestire il contenuto delle stringhe di connessione usate dagli oggetti `Connection` . La classe di base per tutti gli oggetti `ConnectionStringBuilder` è <xref:System.Data.Common.DbConnectionStringBuilder> .|  
|`Parameter`|Definisce i parametri di input, output e dei valori restituiti per i comandi e le stored procedure. La classe di base per tutti gli oggetti `Parameter` è <xref:System.Data.Common.DbParameter> .|  
|`Exception`|Viene restituito quando si verifica un errore nell'origine dati. Per un errore verificatosi nel client, i provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] generano un'eccezione [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . La classe di base per tutti gli oggetti `Exception` è <xref:System.Data.Common.DbException> .|  
|`Error`|Espone le informazioni di un avviso o di un errore restituito da un'origine dati.|  
|`ClientPermission`|Viene fornito per gli attributi di sicurezza dall'accesso di codice del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . La classe di base per tutti gli oggetti `ClientPermission` è <xref:System.Data.Common.DBDataPermission> .|  
  
## <a name="net-framework-data-provider-for-sql-server-sqlclient"></a>Provider di dati .NET Framework per SQL Server (SqlClient)  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server (SqlClient) usa il proprio protocollo per comunicare con SQL Server. È leggera e offre buone prestazioni perché è ottimizzato per l'accesso a SQL Server direttamente senza l'aggiunta di un livello OLE DB oppure Open Database Connectivity (ODBC). Le differenze nella figura seguente il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server con il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per OLE DB. Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB comunica con un'origine dati OLE DB tramite il componente Servizio OLE DB, che fornisce pool di connessioni e servizi di transazione, e il provider OLE DB per l'origine dati.  
  
> [!NOTE]
>  L'architettura del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per ODBC è simile a quella del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB. Come quest'ultimo, ad esempio, effettua una chiamata a un componente Servizio ODBC.  
  
 ![Provider di dati](../../../../docs/framework/data/adonet/media/netdataproviders-bpuedev11.gif "NETDataProviders_bpuedev11")  
Confronto tra il provider di dati .NET Framework per SQL Server e il provider di dati .NET Framework per OLE DB  
  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per le classi di SQL Server si trovano nel <xref:System.Data.SqlClient> dello spazio dei nomi.  
  
 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server, per impostazione predefinita, automaticamente viene integrato in una transazione e ottiene i dettagli di transazione da Servizi componenti di Windows o <xref:System.Transactions>. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.SqlClient` nelle applicazioni.  
  
```vb  
Imports System.Data.SqlClient  
```  
  
```csharp  
using System.Data.SqlClient;  
```  
  
## <a name="net-framework-data-provider-for-ole-db"></a>Provider di dati .NET Framework per OLE DB  
 Per consentire l'accesso ai dati, il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB (OleDb) usa il provider OLE DB nativo tramite l'interoperabilità COM. Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB si inserisce automaticamente, per impostazione predefinita, in una transazione e ottiene i dettagli relativi alla transazione da Servizi componenti di Windows. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nella tabella seguente sono elencati i provider che sono stati testati con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Driver|Provider|  
|------------|--------------|  
|SQLOLEDB|Provider Microsoft OLE DB per SQL Server|  
|MSDAORA|Provider Microsoft OLE DB per Oracle|  
|Microsoft.Jet.OLEDB.4.0|Provider OLE DB per Microsoft Jet|  
  
> [!NOTE]
>  È sconsigliato l'uso di un database Access (Jet) come origine dati per applicazioni con multithreading, quali le applicazioni [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . Se è necessario usare Jet come origine dati per un'applicazione [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] , tenere presente che le applicazioni [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] che si connettono a un database Access possono riscontrare problemi di connessione.  
  
 Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB non supporta le interfacce di OLE DB versione 2.5. I provider OLE DB che richiedono il supporto di interfacce di OLE DB 2.5 non funzioneranno correttamente con il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB. Tra tali provider sono inclusi il provider Microsoft OLE DB per Exchange e il provider Microsoft OLE DB per Internet Publishing.  
  
 Non è possibile usare il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB con il provider OLE DB per ODBC (MSDASQL). Per accedere a un'origine dati ODBC mediante [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], usare il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per ODBC.  
  
 Le classi del provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB sono contenute nello spazio dei nomi <xref:System.Data.OleDb> . Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.OleDb` nelle applicazioni.  
  
```vb  
Imports System.Data.OleDb  
```  
  
```csharp  
using System.Data.OleDb;  
```  
  
## <a name="net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 Per consentire l'accesso ai dati, il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per ODBC (Odbc) usa Gestione driver ODBC. Il provider di dati ODBC supporta transazioni sia locali che distribuite. Per le transazioni distribuite, il provider di dati per ODBC si inserisce automaticamente, per impostazione predefinita, in una transazione e ottiene i dettagli relativi alla transazione da Servizi componenti di Windows. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Nella tabella seguente sono elencati i driver ODBC testati con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
|Driver|  
|------------|  
|SQL Server|  
|Microsoft ODBC per Oracle|  
|Driver per Microsoft Access (*.mdb)|  
  
 Le classi del provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB sono contenute nello spazio dei nomi <xref:System.Data.Odbc> .  
  
 Nell'esempio di codice seguente viene illustrato come includere lo spazio dei nomi `System.Data.Odbc` nelle applicazioni.  
  
```vb  
Imports System.Data.Odbc  
```  
  
```csharp  
using System.Data.Odbc;  
```  
  
> [!NOTE]
>  Per il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per ODBC è richiesto MDAC 2.6 o versione successiva ed è consigliato MDAC 2.8 Service Pack 1 (SP1). È possibile scaricare MDAC 2.8 SP1 da [Archiviazione e accesso ai dati: Centro per sviluppatori](https://go.microsoft.com/fwlink/?linkid=4173).  
  
## <a name="net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle (OracleClient) consente l'accesso alle origini dati Oracle tramite il software di connettività per client Oracle. Il provider di dati può essere usato con il software client Oracle 8.1.7 o versione successiva. Il provider di dati supporta transazioni sia locali che distribuite. Per altre informazioni, vedere [transazioni e concorrenza](../../../../docs/framework/data/adonet/transactions-and-concurrency.md).  
  
 Per usare il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle per la connessione a un'origine dati Oracle, è necessario installare il software client Oracle (versione 8.1.7 o successiva).  
  
 Le classi del provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle sono contenute nello spazio dei nomi <xref:System.Data.OracleClient> , all'interno dell'assembly `System.Data.OracleClient.dll` . Quando si compila un'applicazione in cui viene usato il provider di dati, è necessario fare riferimento sia a `System.Data.dll` che a `System.Data.OracleClient.dll` .  
  
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
 A seconda della struttura e dell'origine dati di un'applicazione, la scelta del provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] più appropriato può migliorare le prestazioni, le funzionalità e l'integrità dell'applicazione. La tabella seguente illustra i vantaggi e i limiti di ogni provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] .  
  
|Provider|Note|  
|--------------|-----------|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server|Consigliato per le applicazioni di livello intermedio che utilizzano Microsoft SQL Server.<br /><br /> Consigliato per applicazioni a un solo livello che utilizzano Microsoft Database Engine (MSDE) o SQL Server.<br /><br /> Consigliato rispetto all'uso del provider OLE DB per SQL Server (SQLOLEDB) con il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per OLE DB.|  
|Provider di dati[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per OLE DB|Per SQL Server, il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per SQL Server è consigliabile invece di questo provider.<br /><br /> Consigliato per applicazioni a un solo livello che usano database di Microsoft Access. L'uso di un database di Microsoft Access per applicazioni di livello intermedio non è consigliato.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per ODBC|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati ODBC.|  
|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per Oracle|Consigliato per applicazioni a un solo livello o a livello intermedio che usano origini dati Oracle.|  
  
## <a name="entityclient-provider"></a>Provider EntityClient  
 Il provider EntityClient è usato per l'accesso ai dati basati su Entity Data Model (EDM). A differenza degli altri provider di dati .NET Framework, non interagisce direttamente con un'origine dati, ma usa Entity SQL per comunicare con il provider di dati sottostante. Per altre informazioni, vedere [EntityClient Provider per Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
