---
title: '&lt;oneWay&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 79dd5dd0ca383cebc5f08f3e12c6c6261d11a02a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltonewaygt"></a>&lt;oneWay&gt;
Abilita il routing dei pacchetti e l'uso di metodi unidirezionali per un'associazione personalizzata.  
  
 \<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<oneWay >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`packetRoutable`|Valore booleano che specifica se è attivato il routing dei pacchetti. Il valore predefinito è `false`.|  
|`MaxAcceptedChannels`|Numero intero che specifica il numero massimo di canali che possono essere accettati.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<channelPoolSettings >](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|Oggetto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> che contiene le proprietà del pool di canali per il canale corrente.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<associazione >](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 Per abilitare il routing dei pacchetti, è necessario un livello di conversione unidirezionale, fornito da questo elemento. Un utente può creare un'associazione personalizzata che sovrapponga questa associazione su un trasporto in grado di riconoscere la sessione o un trasporto Request/Reply affinché supporti il routing dei pacchetti. Questa elemento può essere inoltre usato quando si desidera esporre metodi unidirezionali in modo più nativo. Su questo livello possono essere applicate più trasformazioni, ad esempio duplex composito e messaggistica attendibile.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
