---
title: '&lt;net.tcp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61b799afa1761e59c5cedf5b14eadcaf6fcaada0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltnettcpgt"></a>&lt;net.tcp&gt;
Specifica le impostazioni di configurazione per il servizio di condivisione porte NET.TCP, che consente a più processi di condividere la stessa porta TCP.  
  
 \<system.serviceModel.activation>  
\<net.tcp>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
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
|`listenBacklog`|Numero intero che specifica la quantità massima di connessioni in attesa accettate dalla connessione condivisa, ma che non sono ancora state inviate ai servizi [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Il valore predefinito è 10.|  
|`maxPendingAccepts`|Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione. Il valore predefinito è 2.|  
|`MaxPendingConnections`|Numero massimo di connessioni che il listener può tenere in attesa di essere accettate dall'applicazione. Quando questo valore della quota viene superato, le nuove connessioni in ingresso vengono eliminate anziché restare in attesa di essere accettate. Le funzionalità di connessione, ad esempio la protezione dei messaggi, possono determinare l'apertura di più connessioni da parte di un client. Gli amministratori del servizio devono tener conto delle connessioni aggiuntive durante l'impostazione di questo valore della quota. Il valore predefinito è 10.|  
|`receiveTimeout`|`TimeSpan` che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti. L'impostazione predefinita è "00:00:10".|  
|`teredoEnabled`|Valore booleano che indica se il servizio di condivisione delle porte usa il servizio Microsoft Teredo per l'ascolto sulle porte TCP per conto dei servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<allowAccounts>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Raccolta di elementi di configurazione che contiene un attributo `securityIdentifier` per specificare account utente per processi che ospitano servizi [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] e ai quali è concesso l'accesso al servizio di condivisione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.|  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sulla condivisione delle porte, vedere [condivisione porta Net. TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded). Per comprendere come configurare il servizio di condivisione delle porte, vedere [la configurazione del servizio di condivisione porta Net. TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Condivisione delle porte Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Configurazione del servizio di condivisione delle porte Net.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
