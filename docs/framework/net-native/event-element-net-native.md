---
title: Elemento &lt;Event&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7ccf013398420dbeb7918f99baa922aa1bc89db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="lteventgt-element-net-native"></a>Elemento &lt;Event&gt; (.NET Native)
Applica i criteri di reflection di runtime a un evento.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Event Name="event_name"   
       Browse="policy_type"   
       Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome dell'evento.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni o per l'enumerazione dell'evento, ma non abilita l'accesso dinamico al runtime.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione all'evento per abilitare la programmazione dinamica. Questi criteri assicurano la gestione dinamica di un evento al runtime.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*method_name*|Il nome dell'evento. Il tipo dell'evento viene definito dall'elemento padre [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per l'evento. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Note  
 Se i criteri di un evento non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [Impostazioni dei criteri delle direttive di runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
