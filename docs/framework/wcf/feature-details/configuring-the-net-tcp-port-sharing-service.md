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
# <a name="configuring-the-nettcp-port-sharing-service"></a>Configurazione del servizio di condivisione delle porte Net.TCP
I servizi indipendenti che usano il trasporto Net.TCP possono controllare diverse impostazioni avanzate, quali esempio `ListenBacklog` e `MaxPendingAccepts`, che regolano il comportamento del socket TCP sottostante usato per la comunicazione di rete. Tuttavia, queste impostazioni per ogni socket si applicano solo al livello di associazione, se l'associazione del trasporto ha disattivato la condivisione delle porte, che è attivata per impostazione predefinita.  
  
 Quando un'associazione net.tcp attiva la condivisione delle porte, impostando `portSharingEnabled =true` sull'elemento di associazione del trasporto, consente implicitamente a un processo esterno, ovvero SMSvcHost.exe, che ospita il servizio di condivisione delle porte Net.TCP, di gestire il socket TCP per suo conto. Ad esempio, quando si usa TCP, specificare:  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 Se configurate in questo modo, le impostazioni socket specificate sull'elemento di associazione del trasporto del servizio vengono ignorate a vantaggio delle impostazioni socket specificate da SMSvcHost.exe.  
  
 Per configurare SMSvcHost.exe, creare un file di configurazione XML denominato SmSvcHost.exe.config e posizionarlo nella stessa directory fisica dell'eseguibile SMSvcHost.exe, ad esempio C:\Windows\Microsoft.NET\Framework\v4.5.  
  
 Di seguito viene illustrato un file SMSvcHost.exe.config di esempio, con le impostazioni predefinite per tutti i valori configurabili dichiarate in modo esplicito.  
  
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
  
## <a name="when-to-modify-smsvchostexeconfig"></a>Quando modificare SMSvcHost.exe.config  
 In generale, quando si modifica il contenuto del file SMSvcHost.exe.config è necessario fare attenzione, poiché qualsiasi impostazione di configurazione in esso specificata influenza tutti i servizi presenti in un computer che usa il servizio di condivisione delle porte Net.TCP. Sono incluse le applicazioni in Windows Vista che usano le funzionalità di attivazione TCP del servizio di attivazione dei processi di Windows (WAS).  
  
 Talvolta può però essere necessario modificare la configurazione predefinita del servizio di condivisione delle porte Net.TCP. Ad esempio, il valore predefinito per `maxPendingAccepts` è 4 volte il numero di processori. Nei server che ospitano un gran numero di servizi che usano la condivisione delle porte potrebbe essere necessario aumentare questo valore per raggiungere la velocità effettiva massima. Il valore predefinito di `maxPendingConnections` è 100. Considerare la possibilità di aumentare questo valore se sono presenti più client simultanei che chiamano il servizio e quest'ultimo sta rimuovendo connessioni client.  
  
 SMSvcHost.exe.config contiene inoltre informazioni sulle identità dei processi che potrebbero usare il servizio di condivisione delle porte. Quando un processo si connette al servizio di condivisione delle porte per usare una porta TCP condivisa, l'identità del processo di connessione viene controllata a fronte di un elenco delle identità autorizzate a usare il servizio di condivisione delle porte. Queste identità vengono specificate come ID di sicurezza (SID) nella sezione \<allowAccounts > del file SMSvcHost. exe. config. Per impostazione predefinita, l'autorizzazione a usare il servizio di condivisione delle porte viene concessa agli account di sistema (LocalService, LocalSystem e NetworkService) così come ai membri del gruppo Administrators. Le applicazioni che consentono l'esecuzione di un processo con un'altra identità, ad esempio un'identità utente, per connettersi al servizio di condivisione delle porte, devono aggiungere in modo esplicito il SID appropriato al file SMSvcHost.exe.config. Queste modifiche non vengono applicate fino a quando il processo SMSvc.exe non viene riavviato.  
  
> [!NOTE]
> Nei sistemi Windows Vista con controllo dell'account utente abilitato, gli utenti locali richiedono autorizzazioni elevate anche se il proprio account è un membro del gruppo Administrators. Per consentire a questi utenti di usare il servizio di condivisione delle porte senza elevazione, il SID dell'utente (o il SID di un gruppo di cui l'utente è membro) deve essere aggiunto in modo esplicito alla sezione \<allowAccounts > di SMSvcHost. exe. config.  
  
> [!WARNING]
> Il file SMSvcHost.exe.config predefinito specifica un elemento `etwProviderId` personalizzato per impedire che la traccia di SMSvcHost.exe interferisca con le tracce del servizio.  
  
## <a name="see-also"></a>Vedere anche

- [\<net.tcp>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
