---
title: <PreferComInsteadOfManagedRemoting> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452253"
---
# <a name="prefercominsteadofmanagedremoting-element"></a>\<elemento > PreferComInsteadOfManagedRemoting
Specifica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota per tutte le chiamate tra i limiti del dominio applicazione.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<runtime >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Indica se il runtime utilizzerà l'interoperabilità COM anziché la comunicazione remota tra i limiti del dominio applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Il runtime userà la comunicazione remota tra i limiti del dominio applicazione. Questa è l'impostazione predefinita.|  
|`true`|Il runtime utilizzerà l'interoperabilità COM tra i limiti del dominio applicazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Quando si imposta l'attributo `enabled` su `true`, il runtime si comporta come segue:  
  
- Il runtime non chiama [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) quando un'interfaccia [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) immette il dominio tramite un'interfaccia com. Costruisce invece un [runtime callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) intorno all'oggetto.  
  
- Il runtime restituisce E_NOINTERFACE quando riceve una chiamata `QueryInterface` per un'interfaccia [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) per qualsiasi CCW ( [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) creato in questo dominio.  
  
 Questi due comportamenti assicurano che tutte le chiamate su interfacce COM tra oggetti gestiti tra i limiti del dominio dell'applicazione usino l'interoperabilità COM e COM anziché la comunicazione remota.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che il runtime deve utilizzare l'interoperabilità COM tra i limiti di isolamento:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Schema delle impostazioni di runtime](index.md)
- [Schema dei file di configurazione](../index.md)
