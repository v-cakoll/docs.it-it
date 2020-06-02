---
title: Sintassi delle stringhe di connessione
description: Informazioni sulla sintassi delle stringhe di connessione in ADO.NET. La sintassi per ogni provider è documentata nella relativa proprietà ConnectionString.
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: bb29365a4729e731ddeffc7cfa61e379c3144a46
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287051"
---
# <a name="connection-string-syntax"></a>Sintassi delle stringhe di connessione
Ogni provider di dati .NET Framework include un oggetto `Connection` che eredita da <xref:System.Data.Common.DbConnection> oltre a una proprietà <xref:System.Data.Common.DbConnection.ConnectionString%2A> specifica del provider. La sintassi della stringa di connessione specifica per ogni provider è documentata in questa proprietà `ConnectionString`. Nella tabella seguente sono elencati i quattro provider di dati inclusi in .NET Framework.  
  
|Provider di dati .NET Framework|Descrizione|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|Consente l'accesso ai dati per Microsoft SQL Server. Per altre informazioni sulla sintassi della stringa di connessione, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.|  
|<xref:System.Data.OleDb>|Offre accesso ai dati per le origini dati esposte tramite OLE DB. Per altre informazioni sulla sintassi della stringa di connessione, vedere <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.|  
|<xref:System.Data.Odbc>|Offre accesso ai dati per le origini dati esposte tramite ODBC. Per altre informazioni sulla sintassi della stringa di connessione, vedere <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.|  
|<xref:System.Data.OracleClient>|Offre accesso ai dati per Oracle 8.1.7 o versione successiva. Per altre informazioni sulla sintassi della stringa di connessione, vedere <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.|  
  
## <a name="connection-string-builders"></a>Generatori di stringhe di connessione  
 In ADO.NET 2.0 sono stati introdotti i generatori di stringhe di connessione seguenti per i provider di dati .NET Framework.  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 I generatori di stringhe di connessione consentono di costruire stringhe di connessione sintatticamente valide in fase di esecuzione, pertanto non è necessario concatenare manualmente i valori delle stringhe di connessione nel codice. Per altre informazioni, vedere [Compilatori di stringhe di connessione](connection-string-builders.md).  

## <a name="windows-authentication"></a>Autenticazione di Windows  
 È consigliabile usare l'autenticazione di Windows (talvolta definita *sicurezza integrata*) per connettersi alle origini dati che la supportano. La sintassi usata nella stringa di connessione varia a seconda del provider. La tabella seguente illustra la sintassi dell'autenticazione di Windows usata con i provider di dati .NET Framework.  
  
|Provider|Sintassi|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> `Integrated Security=true` genera un'eccezione se usata con il provider `OleDb`.  
  
## <a name="sqlclient-connection-strings"></a>Stringhe di connessione SqlClient  
La sintassi per una stringa di connessione <xref:System.Data.SqlClient.SqlConnection> è documentata nella proprietà <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>. È possibile usare la proprietà <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> per ottenere o impostare una stringa di connessione per un database di SQL Server. Per eseguire la connessione a una versione precedente di SQL Server, è necessario usare il provider di dati .NET Framework per OleDb (<xref:System.Data.OleDb>). La maggior parte delle parole chiave delle stringhe di connessione sono inoltre mappate alle proprietà dell'oggetto <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  

> [!IMPORTANT]
> L'impostazione predefinita per la `Persist Security Info` parola chiave è `false` . Impostandola su `true` o `yes`, è possibile ottenere informazioni sensibili, compresi l'ID utente e la password, dalla connessione dopo che questa è stata aperta. Mantenere `Persist Security Info` impostata su `false` per assicurarsi che un'origine non attendibile non disponga dell'accesso alle informazioni sensibili sulla stringa di connessione.  

### <a name="windows-authentication-with-sqlclient"></a>Autenticazione di Windows con SqlClient
 Ognuna delle forme di sintassi seguenti usa l'autenticazione di Windows per connettersi al database **AdventureWorks** in un server locale.  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a>Autenticazione SQL Server con SqlClient
 L'autenticazione di Windows è il sistema consigliato per le connessioni a SQL Server. Se tuttavia è necessario usare l'autenticazione di SQL Server, usare la sintassi seguente per specificare un nome utente e una password. In questo esempio per rappresentare un nome utente e una password validi vengono usati asterischi.  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

Quando ci si connette al database SQL di Azure o a Azure SQL Data Warehouse e si specifica un account di accesso nel formato `user@servername` , verificare che il `servername` valore nell'account di accesso corrisponda al valore specificato per `Server=` .

> [!NOTE]
> L'autenticazione di Windows ha la precedenza sugli account di accesso di SQL Server. Se si specifica sia Integrated Security=true sia un nome utente e una password, questi ultimi saranno ignorati e sarà usata l'autenticazione di Windows.  

### <a name="connect-to-a-named-instance-of-sql-server"></a>Connettersi a un'istanza denominata di SQL Server
Per connettersi a un'istanza denominata di SQL Server, utilizzare la sintassi del *nome del server computer\nome* .  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

È anche possibile impostare la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> di `SqlConnectionStringBuilder` sul nome dell'istanza quando si compila una stringa di connessione. La proprietà <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> di un oggetto <xref:System.Data.SqlClient.SqlConnection> è di sola lettura.  
  
### <a name="type-system-version-changes"></a>Modifiche alla versione del sistema di tipi  
 La `Type System Version` parola chiave in un oggetto <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> specifica la rappresentazione lato client dei tipi di SQL Server. Per altre informazioni sulla parola chiave <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>, vedere `Type System Version`.  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a>Connessione e collegamento alle istanze utente di SQL Server Express  
 Le istanze utente sono una funzionalità di SQL Server Express. consentono a un utente che usa un account di Windows locale con privilegi minimi di collegarsi ed eseguire un database SQL Server senza la necessità di privilegi amministrativi. Un'istanza utente viene eseguita con le credenziali di Windows dell'utente, non come un servizio.  
  
 Per ulteriori informazioni sull'utilizzo delle istanze utente, vedere [SQL Server Express istanze utente](./sql/sql-server-express-user-instances.md).  
  
## <a name="using-trustservercertificate"></a>Uso di TrustServerCertificate  
 La `TrustServerCertificate` parola chiave è valida solo quando ci si connette a un'istanza di SQL Server con un certificato valido. Se `TrustServerCertificate` è impostata su `true`, il livello trasporto userà SSL per crittografare il canale e ignorerà l'analisi della catena di certificati per la convalida dell'attendibilità.  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> Se `TrustServerCertificate` è impostata su `true` e la crittografia è attivata, il livello di crittografia specificato nel server verrà usato anche se `Encrypt` è impostato su `false` nella stringa di connessione. In caso contrario, la connessione non riuscirà.  
  
### <a name="enabling-encryption"></a>Abilitazione della crittografia  
 Per abilitare la crittografia quando non è stato eseguito il provisioning di un certificato nel server, è necessario impostare le opzioni **Force Protocol Encryption** e **trust server certificate** in Gestione configurazione SQL Server. In questo caso, la crittografia utilizzerà un certificato server autofirmato senza convalida se nel server non è stato eseguito il provisioning di alcun certificato verificabile.  
  
 Le impostazioni delle applicazioni non possono ridurre il livello di sicurezza configurato in SQL Server, ma facoltativamente possono potenziarlo. Un'applicazione può richiedere la crittografia impostando `TrustServerCertificate` le `Encrypt` parole chiave e su `true` , garantendo che la crittografia venga eseguita anche quando non è stato eseguito il provisioning di un certificato server e non è stata configurata la **crittografia del protocollo** per il client. Tuttavia, se `TrustServerCertificate` non è attivata nella configurazione client, è comunque necessario il provisioning di un certificato server.  
  
 La tabella seguente descrive tutti i casi.  
  
|Impostazione client Forza crittografia protocollo|Impostazione client Considera attendibile certificato server|Attributo/stringa di connessione Encrypt/Use Encryption for Data|Attributo/stringa di connessione Trust Server Certificate|Risultato|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|No|N/D|No (impostazione predefinita)|Ignorato|Nessuna crittografia.|  
|No|N/D|Sì|No (impostazione predefinita)|La crittografia viene applicata solo se è disponibile un certificato server verificabile; in caso contrario, il tentativo di connessione non riesce.|  
|No|N/D|Sì|Sì|La crittografia viene sempre applicata, ma può essere utilizzato un certificato server auto-firmato.|  
|Sì|No|Ignorato|Ignorato|La crittografia viene eseguita solo se è presente un certificato server verificabile; in caso contrario, il tentativo di connessione non riesce.|  
|Sì|Sì|No (impostazione predefinita)|Ignorato|La crittografia viene sempre applicata, ma può essere utilizzato un certificato server auto-firmato.|  
|Sì|Sì|Sì|No (impostazione predefinita)|La crittografia viene eseguita solo se è presente un certificato server verificabile; in caso contrario, il tentativo di connessione non riesce.|  
|Sì|Sì|Sì|Sì|La crittografia viene sempre applicata, ma può essere utilizzato un certificato server auto-firmato.|  
  
 Per altre informazioni, vedere [Uso della crittografia senza convalida](/sql/relational-databases/native-client/features/using-encryption-without-validation).
  
## <a name="oledb-connection-strings"></a>Stringhe di connessione OleDb  
 La proprietà <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> di un oggetto <xref:System.Data.OleDb.OleDbConnection> consente di ottenere o impostare una stringa di connessione per un'origine dati OLE DB quale Microsoft Access. È anche possibile creare una stringa di connessione `OleDb` in fase di esecuzione usando la classe <xref:System.Data.OleDb.OleDbConnectionStringBuilder>.  
  
### <a name="oledb-connection-string-syntax"></a>Sintassi della stringa di connessione OleDb  
 È necessario specificare il nome di un provider per una stringa di connessione <xref:System.Data.OleDb.OleDbConnection>. La seguente stringa di connessione consente di connettersi a un database Microsoft Access usando il provider Jet. Si noti che le parole chiave `User ID` e `Password` sono facoltative se il database non è protetto (impostazione predefinita).  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 Se il database Jet è protetto tramite sicurezza a livello utente, è necessario specificare il percorso del file di informazioni sul gruppo di lavoro, con estensione mdw. Il file di informazioni sul gruppo di lavoro viene usato per convalidare le credenziali fornite nella stringa di connessione.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> È possibile fornire le informazioni di connessione per un oggetto **OleDbConnection** in un file di Universal Data Link (UDL); Tuttavia, è consigliabile evitare di eseguire questa operazione. I file UDL non sono crittografati, pertanto espongono le informazioni nella stringa di connessione come testo non crittografato. Poiché per l'applicazione si tratta di una risorsa esterna basata su file, un file UDL non può essere protetto tramite .NET Framework. I file UDL non sono supportati per **SqlClient**.  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a>Uso di DataDirectory per la connessione a Access/Jet  
 `DataDirectory` non è riservata esclusivamente a `SqlClient`. Può essere usata anche con i provider di dati .NET <xref:System.Data.OleDb> e <xref:System.Data.Odbc>. Nell'esempio seguente la stringa <xref:System.Data.OleDb.OleDbConnection> indica la sintassi richiesta per connettersi al database Northwind.mdb situato nella cartella app_data dell'applicazione. In tale percorso è archiviato anche il database di sistema (System.mdw).  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> Se il database Acces/Jet non è protetto, non è necessario specificare il percorso del database di sistema nella stringa di connessione. La sicurezza è disattivata per impostazione predefinita, con tutti gli utenti che si connettono come utente Admin incorporato con una password vuota. Anche quando la sicurezza a livello di utente è implementata correttamente, un database Jet rimane vulnerabile agli attacchi. Pertanto, considerando la debolezza intrinseca dello schema di sicurezza basato su file dei database Access/Jet, si sconsiglia di archiviare informazioni sensibili in tali database.  
  
### <a name="connecting-to-excel"></a>Connessione a Excel  
 Il provider Microsoft Jet viene usato per la connessione a una cartella di lavoro Excel. Nella seguente stringa di connessione la parola chiave `Extended Properties` imposta le proprietà specifiche di Excel. "HDR=Yes;" indica che la prima riga contiene nomi di colonne e non dati, mentre "IMEX=1;" indica al driver di leggere sempre come testo colonne di dati misti.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 Si noti che le virgolette doppie richieste per `Extended Properties` devono essere racchiuse a loro volta tra virgolette doppie.  
  
### <a name="data-shape-provider-connection-string-syntax"></a>Sintassi della stringa di connessione di Data Shape Provider  
 Con il provider Microsoft Data Shape Provider, usare le parole chiave `Provider` e `Data Provider`. Nell'esempio seguente viene usato il provider Shape per eseguire la connessione a un'istanza locale di SQL Server.  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a>Stringhe di connessione Odbc  
 La proprietà <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> di un oggetto <xref:System.Data.Odbc.OdbcConnection> consente di ottenere o impostare una stringa di connessione per un'origine dati OLE DB. Le stringhe di connessione ODBC sono supportate anche da <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.  
  
 Nella seguente stringa di connessione viene usato il driver Microsoft per file di testo.  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a>Uso di DataDirectory per la connessione a Visual FoxPro  
 Nell'esempio di stringa di connessione <xref:System.Data.Odbc.OdbcConnection> seguente viene illustrato l'uso di `DataDirectory` per eseguire la connessione a un file di Microsoft Visual FoxPro.  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a>Stringhe di connessione Oracle  
 La proprietà <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> di un oggetto <xref:System.Data.OracleClient.OracleConnection> consente di ottenere o impostare una stringa di connessione per un'origine dati OLE DB. Le stringhe di connessione Oracle sono supportate anche da <xref:System.Data.OracleClient.OracleConnectionStringBuilder>.  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 Per altre informazioni sulla sintassi delle stringhe di connessione ODBC, vedere <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Stringhe di connessione](connection-strings.md)
- [Connessione a un'origine dati](connecting-to-a-data-source.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
