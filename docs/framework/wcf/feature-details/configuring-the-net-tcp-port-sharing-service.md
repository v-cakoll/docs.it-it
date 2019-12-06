---
title: Configurazione del servizio di condivisione delle porte Net.TCP
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: 2ff622dc97e63bd0ee10f00c7515692be8df09a1
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837454"
---
# <a name="configuring-the-nettcp-port-sharing-service"></a><span data-ttu-id="15f79-102">Configurazione del servizio di condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="15f79-102">Configuring the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="15f79-103">I servizi indipendenti che usano il trasporto Net.TCP possono controllare diverse impostazioni avanzate, quali esempio `ListenBacklog` e `MaxPendingAccepts`, che regolano il comportamento del socket TCP sottostante usato per la comunicazione di rete.</span><span class="sxs-lookup"><span data-stu-id="15f79-103">Self-hosted services that use the Net.TCP transport can control several advanced settings, such as `ListenBacklog` and `MaxPendingAccepts`, which govern the behavior of the underlying TCP socket used for network communication.</span></span> <span data-ttu-id="15f79-104">Tuttavia, queste impostazioni per ogni socket si applicano solo al livello di associazione, se l'associazione del trasporto ha disattivato la condivisione delle porte, che è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15f79-104">However, these settings for each socket only apply at the binding level if the transport binding has disabled port sharing, which is enabled by default.</span></span>  
  
 <span data-ttu-id="15f79-105">Quando un'associazione net.tcp attiva la condivisione delle porte, impostando `portSharingEnabled =true` sull'elemento di associazione del trasporto, consente implicitamente a un processo esterno, ovvero SMSvcHost.exe, che ospita il servizio di condivisione delle porte Net.TCP, di gestire il socket TCP per suo conto.</span><span class="sxs-lookup"><span data-stu-id="15f79-105">When a net.tcp binding enables port sharing (by setting `portSharingEnabled =true` on the transport binding element), it implicitly allows an external process (namely the SMSvcHost.exe, which hosts the Net.TCP Port Sharing Service) to manage the TCP socket on its behalf.</span></span> <span data-ttu-id="15f79-106">Ad esempio, quando si usa TCP, specificare:</span><span class="sxs-lookup"><span data-stu-id="15f79-106">For example, when using TCP, specify:</span></span>  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 <span data-ttu-id="15f79-107">Se configurate in questo modo, le impostazioni socket specificate sull'elemento di associazione del trasporto del servizio vengono ignorate a vantaggio delle impostazioni socket specificate da SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="15f79-107">When configured in this way, any socket settings specified on the service's transport binding element are ignored in favor of the socket settings specified by SMSvcHost.exe.</span></span>  
  
 <span data-ttu-id="15f79-108">Per configurare SMSvcHost.exe, creare un file di configurazione XML denominato SmSvcHost.exe.config e posizionarlo nella stessa directory fisica dell'eseguibile SMSvcHost.exe, ad esempio C:\Windows\Microsoft.NET\Framework\v4.5.</span><span class="sxs-lookup"><span data-stu-id="15f79-108">To configure the SMSvcHost.exe, create an XML configuration file named SmSvcHost.exe.config and place it in the same physical directory as the SMSvcHost.exe executable (for example, C:\Windows\Microsoft.NET\Framework\v4.5).</span></span>  
  
 <span data-ttu-id="15f79-109">Di seguito viene illustrato un file SMSvcHost.exe.config di esempio, con le impostazioni predefinite per tutti i valori configurabili dichiarate in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="15f79-109">The following example illustrates a sample SMSvcHost.exe.config, with the default settings for all configurable values stated explicitly.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!--16 * # of processors -->  
          maxPendingAccepts="4"<!-- 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!--30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a><span data-ttu-id="15f79-110">Quando modificare SMSvcHost.exe.config</span><span class="sxs-lookup"><span data-stu-id="15f79-110">When to Modify SMSvcHost.exe.config</span></span>  
 <span data-ttu-id="15f79-111">In generale, quando si modifica il contenuto del file SMSvcHost.exe.config è necessario fare attenzione, poiché qualsiasi impostazione di configurazione in esso specificata influenza tutti i servizi presenti in un computer che usa il servizio di condivisione delle porte Net.TCP.</span><span class="sxs-lookup"><span data-stu-id="15f79-111">In general, care should be taken when modifying the contents of the SMSvcHost.exe.config file, because any configuration settings specified in this file affect all of the services on a computer that uses the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="15f79-112">Sono incluse le applicazioni in Windows Vista che usano le funzionalità di attivazione TCP del servizio di attivazione dei processi di Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="15f79-112">This includes applications on Windows Vista that use the TCP Activation features of the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="15f79-113">Talvolta può però essere necessario modificare la configurazione predefinita del servizio di condivisione delle porte Net.TCP.</span><span class="sxs-lookup"><span data-stu-id="15f79-113">However, sometimes you may need to change the default configuration for the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="15f79-114">Ad esempio, il valore predefinito per `maxPendingAccepts` è 4 volte il numero di processori.</span><span class="sxs-lookup"><span data-stu-id="15f79-114">For example, the default value for `maxPendingAccepts` is 4 \* number of processors.</span></span> <span data-ttu-id="15f79-115">Nei server che ospitano un gran numero di servizi che usano la condivisione delle porte potrebbe essere necessario aumentare questo valore per raggiungere la velocità effettiva massima.</span><span class="sxs-lookup"><span data-stu-id="15f79-115">Servers that host a large number of services that use port sharing may increase this value to achieve maximum throughput.</span></span> <span data-ttu-id="15f79-116">Il valore predefinito di `maxPendingConnections` è 100.</span><span class="sxs-lookup"><span data-stu-id="15f79-116">The default value for `maxPendingConnections` is 100.</span></span> <span data-ttu-id="15f79-117">Considerare la possibilità di aumentare questo valore se sono presenti più client simultanei che chiamano il servizio e quest'ultimo sta rimuovendo connessioni client.</span><span class="sxs-lookup"><span data-stu-id="15f79-117">You should consider increasing this value also if there are multiple concurrent clients calling the service and the service is dropping client connections.</span></span>  
  
 <span data-ttu-id="15f79-118">SMSvcHost.exe.config contiene inoltre informazioni sulle identità dei processi che potrebbero usare il servizio di condivisione delle porte.</span><span class="sxs-lookup"><span data-stu-id="15f79-118">SMSvcHost.exe.config also contains information about the process identities that may make use of the port sharing service.</span></span> <span data-ttu-id="15f79-119">Quando un processo si connette al servizio di condivisione delle porte per usare una porta TCP condivisa, l'identità del processo di connessione viene controllata a fronte di un elenco delle identità autorizzate a usare il servizio di condivisione delle porte.</span><span class="sxs-lookup"><span data-stu-id="15f79-119">When a process connects to the port sharing service to make use of a shared TCP port, the process identity of the connecting process is checked against a list of identities that are permitted to make use of the port sharing service.</span></span> <span data-ttu-id="15f79-120">Queste identità vengono specificate come ID di sicurezza (SID) nella sezione \<allowAccounts > del file SMSvcHost. exe. config.</span><span class="sxs-lookup"><span data-stu-id="15f79-120">These identities are specified as security identifiers (SIDs) in the \<allowAccounts> section of the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="15f79-121">Per impostazione predefinita, l'autorizzazione a usare il servizio di condivisione delle porte viene concessa agli account di sistema (LocalService, LocalSystem e NetworkService) così come ai membri del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="15f79-121">By default, permission to use the port sharing service is granted to system accounts (LocalService, LocalSystem, and NetworkService) as well as members of the Administrators group.</span></span> <span data-ttu-id="15f79-122">Le applicazioni che consentono l'esecuzione di un processo con un'altra identità, ad esempio un'identità utente, per connettersi al servizio di condivisione delle porte, devono aggiungere in modo esplicito il SID appropriato al file SMSvcHost.exe.config. Queste modifiche non vengono applicate fino a quando il processo SMSvc.exe non viene riavviato.</span><span class="sxs-lookup"><span data-stu-id="15f79-122">Applications that allow a process running as another identity (for example, a user identity) to connect to the port sharing service must explicitly add the appropriate SID to the SMSvcHost.exe.config (these changes are not applied until the SMSvc.exe process is restarted).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15f79-123">Nei sistemi Windows Vista con controllo dell'account utente abilitato, gli utenti locali richiedono autorizzazioni elevate anche se il proprio account è un membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="15f79-123">On Windows Vista systems with User Account Control (UAC) enabled, local users require elevated permissions even if their account is a member of the Administrators group.</span></span> <span data-ttu-id="15f79-124">Per consentire a questi utenti di usare il servizio di condivisione delle porte senza elevazione, il SID dell'utente (o il SID di un gruppo di cui l'utente è membro) deve essere aggiunto in modo esplicito alla sezione \<allowAccounts > di SMSvcHost. exe. config.</span><span class="sxs-lookup"><span data-stu-id="15f79-124">To allow these users to make use of the port sharing service without elevation, the user's SID (or the SID of a group in which the user is a member) must be explicitly added to the \<allowAccounts> section of SMSvcHost.exe.config.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="15f79-125">Il file SMSvcHost.exe.config predefinito specifica un elemento `etwProviderId` personalizzato per impedire che la traccia di SMSvcHost.exe interferisca con le tracce del servizio.</span><span class="sxs-lookup"><span data-stu-id="15f79-125">The default SMSvcHost.exe.config file specifies a custom `etwProviderId` to prevent SMSvcHost.exe tracing from interfering with service traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f79-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f79-126">See also</span></span>

- [<span data-ttu-id="15f79-127">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="15f79-127">\<net.tcp></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
