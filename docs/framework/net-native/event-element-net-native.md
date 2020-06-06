---
title: <Event>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: e53b029c-9d6d-4c0a-9cdc-5cfca8a5ca47
ms.openlocfilehash: 60da48d5872d7ce61afcffa7977411bc6e1efc7f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181033"
---
# <a name="event-element-net-native"></a>\<Event>Elemento (.NET Native)
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
  
|Valore|Description|  
|-----------|-----------------|  
|*method_name*|Nome dell'evento. Il tipo dell'evento viene definito dall' [\<Type>](type-element-net-native.md) elemento padre o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Valore|Description|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per l'evento. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Commenti  
 Se i criteri di un evento non sono definiti esplicitamente, l'evento eredita i criteri di runtime dell'elemento padre.  
  
## <a name="see-also"></a>Vedi anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Impostazioni dei criteri della direttiva di runtime](runtime-directive-policy-settings.md)
