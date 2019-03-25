---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 90d081c1287362669286aaa1185ed3b0bbe09b07
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412110"
---
# <a name="netpipe"></a>\<net.pipe>
Specifica impostazioni di configurazione per Named Pipe Activation Service, che gestisce la durata della connessione named pipe, nonché le richieste di attivazione che arrivano sulle named pipe.  
  
 \<system.serviceModel.activation>  
\<net.pipe>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maxPendingAccepts`|Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione. Il valore predefinito è 2.|  
|`maxPendingConnections`|Numero intero che specifica il numero massimo di connessioni che possono rimanere in attesa di invio. Il valore predefinito è 100.|  
|`receiveTimeout`|
  <xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti. L'impostazione predefinita è "00:00:10".|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Una raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per processi che ospitano servizi WCF e vengono concesso l'accesso al servizio di condivisione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
