---
title: <Namespace>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7be004776d2a2fd3b4c41fb21b3ac244946f2166
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049421"
---
# <a name="namespace-element-net-native"></a>\<Elemento > dello spazio dei nomi (.NET Native)
Applica i criteri di reflection di runtime a tutti i tipi in un determinato spazio dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type"  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
           DataContractSerializer="policy_setting"  
           DataContractJsonSerializer="policy_setting"  
           XmlSerializer="policy_setting"  
           MarshalObject="policy_setting"  
           MarshalDelegate="policy_setting"  
           MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|DESCRIZIONE|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome dello spazio dei nomi.|  
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|  
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.|  
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|  
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling delle strutture al codice nativo.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|*namespace_name*|Nome dello spazio dei nomi. Se l'elemento \<Namespace> è figlio di un elemento [\<Application>](application-element-net-native.md), [\<Library>](library-element-net-native.md) o [\<Assembly>](assembly-element-net-native.md), *namespace_name* deve essere un nome completo dello spazio dei nomi. Se l'elemento \<Namespace> è figlio di un altro elemento \<Namespace>, *namespace_name* deve essere un nome relativo dello spazio dei nomi.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per tutti i tipi nello spazio dei nomi. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`<Namespace>`|Applica i criteri di reflection di runtime a tutti i tipi in uno spazio dei nomi padre.|  
|[\<Type>](type-element-net-native.md)|Applica i criteri di reflection a un tipo.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection al runtime. L'elemento [\<Application>](application-element-net-native.md) può contenere nessuno, uno o più elementi [\<Assembly>](assembly-element-net-native.md).|  
|[\<Assembly>](assembly-element-net-native.md)|Applica i criteri di reflection di runtime a tutti i tipi in un determinato assembly.|  
|[\<Library>](library-element-net-native.md)|Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime. L'elemento [\<Library>](library-element-net-native.md) può contenere nessuno o un elemento [\<Assembly>](assembly-element-net-native.md).|  
|`<Namespace>`|Applica i criteri di reflection a tutti i tipi in uno spazio dei nomi padre.|  
  
## <a name="remarks"></a>Note  
 Gli attributi `Activate`, `Browse`, `Dynamic` e `Serialize` sono tutti facoltativi. Se non ne è presente nessuno, l'elemento `<Namespace>` funge solo da contenitore per gli elementi figlio. Se sono presenti, l'elemento `<Namespace>` consente di applicare criteri di reflection di runtime a tutti i tipi dello spazio dei nomi specificato.  
  
 Quando è figlio dell'elemento [\<Assembly>](assembly-element-net-native.md), l'elemento `<Namespace>` prevale sui criteri di reflection di runtime definiti dall'elemento [\<Assembly>](assembly-element-net-native.md).  
  
## <a name="see-also"></a>Vedere anche

- [Impostazioni dei criteri delle direttive di runtime](runtime-directive-policy-settings.md)
- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
