---
title: Elemento &lt;Field&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b713eefa4f23aec34b5f55c0c3457381f54ef931
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ltfieldgt-element-net-native"></a>Elemento &lt;Field&gt; (.NET Native)
Applica i criteri di reflection di runtime a un campo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome del campo.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni o per l'enumerazione del campo, ma non abilita l'accesso dinamico al runtime.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione al campo per abilitare la programmazione dinamica. Questo criterio assicura che un campo può essere impostato o recuperato dinamicamente in fase di esecuzione.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a un campo per abilitare le istanze di tipo da serializzare in librerie quali il serializzatore JSON Newtonsoft o da usare per il data binding.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*method_name*|Nome del campo. Il tipo del campo viene definito dall'elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) padre.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per il campo. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Note  
 Se i criteri di un campo non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.  
  
## <a name="see-also"></a>Vedere anche  
 [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [Impostazioni dei criteri delle direttive di runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
