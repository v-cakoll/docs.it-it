---
title: Novità
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: 2ac8ebced700dc6c874ac22304773b3b9c19f8b3
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979762"
---
# <a name="whats-new-in-adonet"></a>Novità in ADO.NET

Le funzionalità seguenti sono nuove in ADO.NET nella .NET Framework 4,5.

## <a name="sqlclient-data-provider"></a>Provider di dati SqlClient

Le funzionalità seguenti sono nuove nell'provider di dati di .NET Framework per SQL Server in .NET Framework 4,5:

- Le parole chiave della stringa di connessione ConnectRetryCount e ConnectRetryInterval (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) consentono di controllare la funzionalità di resilienza di una connessione inattiva.

- Il supporto del flusso da SQL Server a un'applicazione supporta scenari in cui i dati nel server non sono strutturati.  Per ulteriori informazioni, vedere [supporto del flusso SqlClient](sqlclient-streaming-support.md) .

- È stato aggiunto il supporto per la programmazione asincrona.  Per ulteriori informazioni, vedere [programmazione asincrona](asynchronous-programming.md) .

- Gli errori di connessione verranno registrati nel registro eventi esteso. Per altre informazioni, vedere [Traccia dati in ADO.NET](data-tracing.md).

- SqlClient dispone ora del supporto per la funzionalità di ripristino di emergenza e disponibilità elevata SQL Server, AlwaysOn. Per ulteriori informazioni, vedere il [supporto SqlClient per la disponibilità elevata e il ripristino di emergenza](./sql/sqlclient-support-for-high-availability-disaster-recovery.md).

- Una password può essere passata come <xref:System.Security.SecureString> quando si usa l'autenticazione di SQL Server. Per altre informazioni, vedere <xref:System.Data.SqlClient.SqlCredential>.

- Quando `TrustServerCertificate` è false e `Encrypt` è true, il nome del server (o indirizzo IP) in un certificato SSL SQL Server deve corrispondere esattamente al nome del server (o indirizzo IP) specificato nella stringa di connessione. In caso contrario, il tentativo di connessione non riuscirà. Per altre informazioni, vedere la descrizione dell'opzione di connessione `Encrypt` in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

  Se questa modifica impedisce a un'applicazione esistente di stabilire una connessione in futuro, è possibile correggere l'applicazione usando una delle operazioni seguenti:

  - Rilasciare un certificato che specifichi il nome breve nel campo relativo al nome comune (CN) o al nome alternativo del soggetto (SAN). Questa soluzione funzionerà per il mirroring del database.

  - Aggiungere un alias che esegua il mapping del nome breve al nome di dominio completo.

  - Usare il nome di dominio completo nella stringa di connessione.

- SqlClient supporta la protezione estesa. Per ulteriori informazioni sulla protezione estesa, vedere [connessione al motore di database mediante la protezione estesa](/sql/database-engine/configure-windows/connect-to-the-database-engine-using-extended-protection).

- SqlClient supporta le connessioni ai database LocalDB. Per ulteriori informazioni, vedere [supporto SqlClient per il database locale](./sql/sqlclient-support-for-localdb.md).

- `Type System Version=SQL Server 2012;` è il nuovo valore da passare alla proprietà di connessione `Type System Version`. Il valore `Type System Version=Latest;` è obsoleto ed è diventato equivalente a `Type System Version=SQL Server 2008;`. Per ulteriori informazioni, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

- SqlClient fornisce supporto aggiuntivo per le colonne di tipo sparse, una funzionalità aggiunta in SQL Server 2008. Se l'applicazione accede già ai dati in una tabella che usa colonne di tipo sparse, si sarà notato un aumento delle prestazioni. La colonna IsColumnSet di <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> indica se una colonna è di tipo sparse, ovvero membro di un set di colonne. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> indica se una colonna è una colonna di tipo sparse. per ulteriori informazioni, vedere [SQL Server raccolte di schemi](sql-server-schema-collections.md) . Per ulteriori informazioni sulle colonne di tipo sparse, vedere [utilizzo di colonne di tipo sparse](/sql/relational-databases/tables/use-sparse-columns).

- L'assembly Microsoft.SqlServer.Types.dll, che contiene i tipi di dati spaziali, è stato aggiornato dalla versione 10.0 alla versione 11.0. Le applicazioni che fanno riferimento a questo assembly potrebbero avere esito negativo. Per ulteriori informazioni, vedere [modifiche di rilievo alle funzionalità di motore di database](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/ms143179(v=sql.110)).

## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework

Il .NET Framework 4,5 aggiunge API che consentono nuovi scenari quando si lavora con Entity Framework 5,0. Per ulteriori informazioni sui miglioramenti e sulle funzionalità aggiunti alla Entity Framework 5,0, [vedere gli argomenti seguenti: novità](https://docs.microsoft.com/previous-versions/gg696190(v=vs.103)) e [Entity Framework versioni e controllo delle versioni](/ef/ef6/what-is-new/past-releases).

## <a name="see-also"></a>Vedere anche

- [ADO.NET](index.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
- [SQL Server e ADO.NET](./sql/index.md)
- [Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
