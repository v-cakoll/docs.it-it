---
title: Novità in ADO.NET
ms.date: 03/30/2017
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
ms.openlocfilehash: b54f7ab6505f86d0447654f21b197644d68254c0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583443"
---
# <a name="whats-new-in-adonet"></a>Novità in ADO.NET

Di seguito sono riportate le nuove funzionalità di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].

## <a name="sqlclient-data-provider"></a>Provider di dati SqlClient

Le funzionalità seguenti sono nuove in Provider di dati .NET Framework per SQL Server in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]:

- Le parole chiave della stringa di connessione ConnectRetryCount e ConnectRetryInterval (<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>) consentono di controllare la funzionalità di resilienza di una connessione inattiva.

- Supporto del flusso da SQL Server a un'applicazione supporta scenari in cui i dati nel server sono dati non strutturati.  Visualizzare [supporto del flusso SqlClient](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md) per altre informazioni.

- È stato aggiunto il supporto per la programmazione asincrona.  Visualizzare [programmazione asincrona](../../../../docs/framework/data/adonet/asynchronous-programming.md) per altre informazioni.

- Gli errori di connessione verranno registrati nel registro eventi esteso. Per altre informazioni, vedere [Traccia dati in ADO.NET](../../../../docs/framework/data/adonet/data-tracing.md).

- SqlClient ora offre supporto per la disponibilità elevata SQL Server, funzionalità di ripristino di emergenza, AlwaysOn. Per altre informazioni, vedere [supporto SqlClient per disponibilità elevata, ripristino di emergenza](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

- Una password può essere passata come un <xref:System.Security.SecureString> quando si usa l'autenticazione di SQL Server. Per altre informazioni, vedere <xref:System.Data.SqlClient.SqlCredential>.

- Quando `TrustServerCertificate` è false e `Encrypt` è true, il nome del server (o l'indirizzo IP) in un certificato SSL di SQL Server deve corrispondere esattamente il server name (o indirizzo IP) specificato nella stringa di connessione. In caso contrario, il tentativo di connessione non riuscirà. Per altre informazioni, vedere la descrizione dell'opzione di connessione `Encrypt` in <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

  Se questa modifica impedisce a un'applicazione esistente di stabilire una connessione in futuro, è possibile correggere l'applicazione usando una delle operazioni seguenti:

  - Rilasciare un certificato che specifichi il nome breve nel campo relativo al nome comune (CN) o al nome alternativo del soggetto (SAN). Questa soluzione funzionerà per il mirroring del database.

  - Aggiungere un alias che esegua il mapping del nome breve al nome di dominio completo.

  - Usare il nome di dominio completo nella stringa di connessione.

- SqlClient supporta la protezione estesa. Per altre informazioni sulla protezione estesa, vedere [la connessione al motore di Database usando estesi protezione](https://go.microsoft.com/fwlink/?LinkId=219978).

- SqlClient supporta le connessioni ai database LocalDB. Per altre informazioni, vedere [supporto SqlClient per LocalDB](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md).

- `Type System Version=SQL Server 2012;` è il nuovo valore da passare alla proprietà di connessione `Type System Version`. Il valore `Type System Version=Latest;` è obsoleto ed è diventato equivalente a `Type System Version=SQL Server 2008;`. Per altre informazioni, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.

- SqlClient fornisce supporto aggiuntivo per le colonne di tipo sparse, una funzionalità aggiunta in SQL Server 2008. Se l'applicazione accede già ai dati in una tabella che usa colonne di tipo sparse, si noterà un miglioramento delle prestazioni. La colonna IsColumnSet di <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> indica se una colonna è di tipo sparse, ovvero membro di un set di colonne. <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> indica se una colonna è di tipo sparse (vedere [raccolte di schemi di SQL Server](../../../../docs/framework/data/adonet/sql-server-schema-collections.md) per altre informazioni). Per altre informazioni sulle colonne di tipo sparse, vedere [utilizzo di colonne di tipo Sparse](https://go.microsoft.com/fwlink/?LinkId=224244).

- L'assembly Microsoft.SqlServer.Types.dll, che contiene i tipi di dati spaziali, è stato aggiornato dalla versione 10.0 alla versione 11.0. Le applicazioni che fanno riferimento a questo assembly potrebbero avere esito negativo. Per altre informazioni, vedere [le modifiche di rilievo alle funzionalità del motore di Database](https://go.microsoft.com/fwlink/?LinkId=224367).

## <a name="adonet-entity-framework"></a>ADO.NET Entity Framework

In [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] sono state aggiunte le API che abilitano nuovi scenari quando si usa Entity Framework 5.0. Per altre informazioni sui miglioramenti e funzionalità che sono stati aggiunti a Entity Framework 5.0, vedere gli argomenti seguenti: [Quali sono le novità](https://go.microsoft.com/fwlink/?LinkID=251106) e [le versioni di Entity Framework e il controllo delle versioni](https://go.microsoft.com/fwlink/?LinkId=234899).

## <a name="see-also"></a>Vedere anche

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [SQL Server e ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)
- [Quali sono le novità in WCF Data Services 5.0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
