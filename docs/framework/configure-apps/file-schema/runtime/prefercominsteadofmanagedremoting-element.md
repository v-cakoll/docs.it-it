---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745474"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; elemento
Specifica se il runtime utilizzerà l'interoperabilità COM anziché remoti per tutte le chiamate tra i limiti del dominio applicazione.  
  
 \<configuration>  
\<runtime>  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se il runtime utilizzerà l'interoperabilità COM anziché remoting limiti del dominio applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il runtime utilizza comunicazione remota di limiti del dominio applicazione. Questa è l'impostazione predefinita.|  
|`true`|Il runtime utilizzerà l'interoperabilità COM limiti del dominio applicazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando si imposta la `enabled` attributo `true`, il runtime si comporta come segue:  
  
-   Il runtime non chiami [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia quando un [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interfaccia accede al dominio tramite un'interfaccia COM. Invece, costruisce una [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) attorno all'oggetto.  
  
-   Il runtime restituisce E_NOINTERFACE quando riceve un `QueryInterface` chiamare per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia per qualsiasi [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) che è stato creato in questo dominio.  
  
 Questi due comportamenti assicurarsi che tutte le chiamate tramite COM interfacce tra gli oggetti gestiti attraverso l'utilizzo di limiti di dominio dell'applicazione COM e l'interoperabilità COM anziché servizi remoti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare COM interoperabilità attraverso i limiti di isolamento:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
