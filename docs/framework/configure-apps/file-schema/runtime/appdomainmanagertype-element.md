---
title: '&lt;appDomainManagerType&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfdd9bcd1aa458aad705d4ab129646e746d63b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainmanagertypegt-element"></a>&lt;appDomainManagerType&gt; elemento
Specifica il tipo che funge da gestore di dominio dell'applicazione per il dominio applicazione predefinito.  
  
 \<configuration>  
\<runtime >  
\<appDomainManagerType >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`value`|Attributo obbligatorio. Specifica il nome del tipo, incluso lo spazio dei nomi, che funge da gestore di dominio di applicazione per il dominio applicazione predefinito nel processo.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Per specificare il tipo del gestore di dominio di applicazione, è necessario specificare sia questo elemento e [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento. Se uno di questi elementi non è specificato, l'altro viene ignorato.  
  
 Quando il dominio applicazione predefinito viene caricato, <xref:System.TypeLoadException> viene generata se il tipo specificato non esiste nell'assembly specificato da di [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento; e non il processo avviare.  
  
 Quando si specifica il tipo di gestore di dominio di applicazione per il dominio applicazione predefinito, gli altri domini applicazione creati dal dominio applicazione predefinito ereditano il tipo di gestione del dominio applicazione. Utilizzare il <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> e <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> le proprietà per specificare un tipo di gestione del dominio applicazione diverso per un nuovo dominio applicazione.  
  
 Specifica il tipo di gestione del dominio applicazione richiede che l'applicazione disponga di attendibilità. (Ad esempio, un'applicazione in esecuzione sul desktop è l'attendibilità totale.) Se l'applicazione non ha l'attendibilità totale, un <xref:System.TypeLoadException> viene generata un'eccezione.  
  
 Il formato del tipo e spazio dei nomi è lo stesso formato utilizzato per la <xref:System.Type.FullName%2A?displayProperty=nameWithType> proprietà.  
  
 È disponibile solo in questo elemento di configurazione di [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il gestore di dominio di applicazione per il dominio applicazione predefinito di un processo è il `MyMgr` digitare il `AdMgrExample` assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [\<appDomainManagerAssembly > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Metodo SetAppDomainManagerType](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
