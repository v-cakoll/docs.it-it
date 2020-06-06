---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397689"
---
# \<net.tcp>
Specifica le impostazioni di configurazione per il servizio di condivisione porte NET.TCP, che consente a più processi di condividere la stessa porta TCP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
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
|`listenBacklog`|Numero intero che specifica il numero massimo di connessioni in attesa accettate dalla connessione condivisa, ma che non sono ancora state inviate ai servizi Windows Communication Foundation (WCF). Il valore predefinito è 10.|  
|`maxPendingAccepts`|Numero intero che specifica il massimo di thread di accettazione contemporaneamente in attesa sull'endpoint di ascolto per il servizio di condivisione. Il valore predefinito è 2.|  
|`MaxPendingConnections`|Numero massimo di connessioni che il listener può tenere in attesa di essere accettate dall'applicazione. Quando questo valore della quota viene superato, le nuove connessioni in ingresso vengono eliminate anziché restare in attesa di essere accettate. Le funzionalità di connessione, ad esempio la protezione dei messaggi, possono determinare l'apertura di più connessioni da parte di un client. Gli amministratori del servizio devono tener conto delle connessioni aggiuntive durante l'impostazione di questo valore della quota. Il valore predefinito è 10.|  
|`receiveTimeout`|<xref:System.TimeSpan> che specifica il timeout per la lettura dei dati sui frame e per l'esecuzione dell'invio della connessione dalle connessioni sottostanti. L'impostazione predefinita è "00:00:10".|  
|`teredoEnabled`|Valore booleano che indica se il servizio di condivisione delle porte utilizza il servizio Microsoft Teredo per l'ascolto sulle porte TCP per conto dei servizi WCF. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|Raccolta di elementi di configurazione che contengono un `securityIdentifier` attributo per specificare gli account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|Contiene impostazioni di configurazione per il processo del listener SMSvcHost.exe.|  
  
## <a name="remarks"></a>Commenti  
 Per ulteriori informazioni sulla condivisione delle porte, vedere la pagina relativa alla [condivisione delle porte net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md). Per informazioni su come configurare il servizio di condivisione delle porte, vedere [configurazione del servizio di condivisione porte net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [Condivisione delle porte Net.TCP](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [Configurazione del servizio di condivisione delle porte Net.TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
