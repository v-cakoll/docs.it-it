---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 760eeeaaf82bf2014d70fa79ced2bb9166a8cb60
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613271"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; elemento
Specifica se il runtime userà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se il runtime userà l'interoperabilità COM anziché la comunicazione remota attraverso i limiti del dominio applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il runtime Usa .NET remoting superando i limiti di dominio di applicazione. Questa è l'impostazione predefinita.|  
|`true`|Il runtime userà l'interoperabilità COM superando i limiti di dominio di applicazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando si impostano i `enabled` dell'attributo `true`, il runtime si comporta come segue:  
  
-   Il runtime non chiami [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) per un' [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia quando un' [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interfaccia accede al dominio tramite un'interfaccia COM. In alternativa, crea una [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) attorno all'oggetto.  
  
-   E_NOINTERFACE viene restituito dal runtime quando riceve un `QueryInterface` chiamare per un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaccia per qualsiasi [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) che è stato creato in questo dominio.  
  
 Questi due comportamenti assicurarsi che tutte le chiamate su COM interfacce tra gli oggetti gestiti attraverso l'utilizzo dei limiti di dominio dell'applicazione COM e l'interoperabilità COM anziché la comunicazione remota.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare COM interoperabilità tra i limiti di isolamento:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
