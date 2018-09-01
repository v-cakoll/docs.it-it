---
title: Supporto SqlClient per disponibilità elevata, ripristino di emergenza
ms.date: 03/30/2017
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
ms.openlocfilehash: 258922a1541c4594ce2b4673d4d68c279087aef2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395855"
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a>Supporto SqlClient per disponibilità elevata, ripristino di emergenza
In questo argomento viene descritto il supporto di SqlClient (aggiunto in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]) per i gruppi di disponibilità AlwaysOn, con disponibilità elevata e ripristino di emergenza.  La funzionalità gruppi di disponibilità AlwaysOn è stato aggiunto a SQL Server 2012. Per altre informazioni sui gruppi di disponibilità AlwaysOn, vedere la documentazione Online di SQL Server.  
  
 È ora possibile specificare il listener del gruppo di disponibilità di un (disponibilità elevata, ripristino di emergenza) il gruppo di disponibilità (AG) o istanza Cluster di Failover SQL Server 2012 nella proprietà di connessione. Se un'applicazione di SqlClient è connessa a un database AlwaysOn che esegue il failover, la connessione originale viene interrotta e l'applicazione deve aprire una nuova connessione per continuare a funzionare dopo il failover.  
  
 Se non ci si connette a un listener del gruppo di disponibilità o l'istanza del Cluster di Failover di SQL Server 2012 e se più indirizzi IP sono associati un nome host, SqlClient scorrerà in sequenza tutti gli indirizzi IP associati alla voce DNS. Ciò può richiedere molto tempo se il primo indirizzo IP restituito dal server DNS non è associato a una scheda di interfaccia di rete (NIC). Quando ci si connette a un listener del gruppo di disponibilità o l'istanza del Cluster di Failover di SQL Server 2012, SqlClient tenta di stabilire connessioni a tutti gli indirizzi IP in parallelo e se un tentativo di connessione ha esito positivo, il driver verrà rimosso qualsiasi connessione in sospeso tentativi.  
  
> [!NOTE]
>  L'aumento del timeout di connessione e l'implementazione di una logica di ripetizione dei tentativi di connessione aumenterà la probabilità che un'applicazione si connetta a un gruppo di disponibilità. Inoltre, poiché una connessione può avere esito negativo a causa di un failover, è necessario implementare la logica di ripetizione dei tentativi di connessione, in modo che una connessione non riuscita venga ripetuta finché non avrà esito positivo.  
  
 Le seguenti proprietà di connessione sono state aggiunte a SqlClient in [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]:  
  
-   `ApplicationIntent`  
  
-   `MultiSubnetFailover`  
  
 A livello di programmazione è possibile modificare queste parole chiave della stringa di connessione con:  
  
1.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2.  <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
>  L'impostazione `MultiSubnetFailover` al `true` non è obbligatorio con [!INCLUDE[net_v461](../../../../../includes/net-v461-md.md)] o versioni successive.
  
## <a name="connecting-with-multisubnetfailover"></a>Connessione con MultiSubnetFailover  
 Specificare sempre `MultiSubnetFailover=True` quando ci si connette a un listener del gruppo di disponibilità di SQL Server 2012 o istanza del Cluster di Failover di SQL Server 2012. `MultiSubnetFailover` Abilita il failover più veloce per tutti i gruppi di disponibilità e o istanza del Cluster di Failover in SQL Server 2012 e sarà ridurre significativamente il tempo di failover per le topologie AlwaysOn singole e su più subnet. Durante il failover di più subnet, il client tenterà di stabilire connessioni in parallelo. Durante il failover di una subnet, riproverà continuamente la connessione TCP.  
  
 Il `MultiSubnetFailover` proprietà di connessione indica che l'applicazione viene distribuita in un gruppo di disponibilità o l'istanza del Cluster di Failover di SQL Server 2012 e che SqlClient tenterà di connettersi al database nell'istanza di SQL Server primaria tentando di connettersi a tutti gli indirizzi IP. Quando si specifica `MultiSubnetFailover=True` per una connessione, il client ripete i tentativi di connessione TCP più velocemente degli intervalli di ritrasmissione TCP predefiniti del sistema operativo. In questo modo viene abilitata la riconnessione più veloce dopo il failover di un gruppo di disponibilità AlwaysOn o di un'istanza del cluster di failover AlwaysOn ed è applicabile sia ai gruppi di disponibilità che alle istanze del cluster di failover con più subnet.  
  
 Per altre informazioni sulle parole chiave della stringa di connessione in SqlClient, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Specifica di `MultiSubnetFailover=True` quando ci si connette a un elemento diverso da un listener del gruppo di disponibilità o l'istanza del Cluster di Failover di SQL Server 2012 può comportare un impatto negativo sulle prestazioni e non è supportato.  
  
 Usare le linee guida seguenti per connettersi a un server in un gruppo di disponibilità o istanza del Cluster di Failover di SQL Server 2012:  
  
-   Usare la proprietà di connessione `MultiSubnetFailover` quando ci si connette a una o più subnet per ottenere un miglioramento delle prestazioni di entrambi.  
  
-   Per connettersi a un gruppo di disponibilità, specificare il listener gruppo di disponibilità come server nella stringa di connessione.  
  
-   La connessione a SQL Server istanza configurata con più di 64 indirizzi IP causerà un errore di connessione.  
  
-   Comportamento di un'applicazione che utilizza il `MultiSubnetFailover` proprietà di connessione non è interessata in base al tipo di autenticazione: autenticazione di SQL Server, l'autenticazione Kerberos o autenticazione di Windows.  
  
-   Aumentare il valore di `Connect Timeout` per adattarlo al tempo di failover e ridurre i tentativi di connessione dell'applicazione.  
  
-   Le transazioni distribuite non sono supportate.  
  
 Se il routing di sola lettura non è attivo, la connessione a un percorso di replica secondaria avrà esito negativo nelle seguenti situazioni:  
  
1.  Se il percorso di replica secondaria non è configurato per accettare connessioni.  
  
2.  Se un'applicazione usa `ApplicationIntent=ReadWrite` (illustrato di seguito) e il percorso di replica secondaria è configurato per l'accesso di sola lettura.  
  
 <xref:System.Data.SqlClient.SqlDependency> non è supportato per le repliche secondarie di sola lettura.  
  
 Una connessione non riuscirà se una replica primaria è configurata per rifiutare i carichi di lavoro di sola lettura e la stringa di connessione contiene `ApplicationIntent=ReadOnly`.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>Aggiornamento per l'uso di cluster con più subnet dal mirroring del database  
 Si verificherà un errore di connessione (<xref:System.ArgumentException>) se nella stringa di connessione sono presenti le parole chiave di connessione `MultiSubnetFailover` e `Failover Partner` o se vengono usati `MultiSubnetFailover=True` e un protocollo diverso da TCP. Un errore (<xref:System.Data.SqlClient.SqlException>) si verificherà anche se `MultiSubnetFailover` viene usato e il Server SQL restituisce una risposta di partner di failover indicato fa parte di una coppia di mirroring del database.  
  
 Se si aggiorna un'applicazione SqlClient che attualmente usa il mirroring del database in uno scenario con più subnet, è necessario rimuovere la proprietà di connessione `Failover Partner` e sostituirla con `MultiSubnetFailover` impostata su `True` e sostituire il nome del server nella stringa di connessione con un listener gruppo di disponibilità. Se in una stringa di connessione si usa `Failover Partner` e `MultiSubnetFailover=True`, il driver genererà un errore. Se tuttavia in una stringa di connessione si usa `Failover Partner` e `MultiSubnetFailover=False` (o `ApplicationIntent=ReadWrite`), l'applicazione utilizzerà il mirroring del database.  
  
 Il driver restituirà un errore se il mirroring del database viene usato nel database primario del gruppo di disponibilità e se `MultiSubnetFailover=True` viene usata nella stringa di connessione che si connette a un database primario anziché a un listener gruppo di disponibilità.  
  
## <a name="specifying-application-intent"></a>Impostazione della finalità dell'applicazione  
 Se `ApplicationIntent=ReadOnly`, il client richiede un carico di lavoro di lettura quando si connette a un database abilitato per AlwaysOn. Il server applicherà la finalità al momento della connessione e durante un'istruzione USE del database, ma solo a un database abilitato per AlwaysOn.  
  
 La parola chiave `ApplicationIntent` non funziona con i database legacy di sola lettura.  
  
 Un database può consentire o non consentire carichi di lavoro di lettura nel database AlwaysOn di destinazione. Questa operazione viene eseguita con la clausola `ALLOW_CONNECTIONS` delle istruzioni `PRIMARY_ROLE` e `SECONDARY_ROLE`[!INCLUDE[tsql](../../../../../includes/tsql-md.md)].  
  
 La parola chiave `ApplicationIntent` viene usata per abilitare il routing di sola lettura.  
  
## <a name="read-only-routing"></a>Routing di sola lettura  
 Il routing di sola lettura è una funzionalità che può garantire la disponibilità di una replica di sola lettura di un database. Per abilitare il routing di sola lettura:  
  
1.  È necessario connettersi a un listener gruppo di disponibilità di un gruppo di disponibilità AlwaysOn.  
  
2.  La parola chiave della stringa di connessione `ApplicationIntent` deve essere impostata su `ReadOnly`.  
  
3.  Il gruppo di disponibilità deve essere configurato dall'amministratore del database in modo da abilitare il routing di sola lettura.  
  
 È possibile che più connessioni che usano il routing di sola lettura non si connettano tutte alla stessa replica di sola lettura. Le modifiche apportate alla sincronizzazione del database o alla configurazione del routing del server possono comportare connessioni client a repliche di sola lettura diverse. Per accertarsi che tutte le richieste di sola lettura si connettano alla stessa replica di sola lettura, non passare un listener gruppo di disponibilità alla parola chiave della stringa di connessione `Data Source`. Specificare invece il nome dell'istanza di sola lettura.  
  
 Il routing di sola lettura può richiedere più tempo rispetto alla connessione al database primario, poiché il routing di sola lettura si connette innanzitutto al database primario, quindi effettua la ricerca del miglior database secondario leggibile disponibile. Per questo motivo, è necessario aumentare il timeout di accesso.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzionalità di SQL Server e ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
