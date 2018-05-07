---
title: Elemento &lt;Application&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60145611981b53d4778e7c52c6138b6a9b58a592
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ltapplicationgt-element-net-native"></a>Elemento &lt;Application&gt; (.NET Native)
Funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione e applica criteri di reflection di runtime a tutti gli elementi del programma in un'applicazione.  
  
 Elemento \<Directives>  
Elemento \<Application> (rd.xml)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Application Activate="policy_setting"  
             Browse="policy_setting"  
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
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre. Nella tabella degli elementi figlio, i criteri fanno riferimento al tipo di metadati che vengono resi disponibili per gli elementi del programma specifico in fase di esecuzione.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni o per l'enumerazione dei tipi, ma non abilita l'accesso dinamico al runtime.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|  
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.|  
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|  
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per il marshalling delle strutture al codice nativo.|  
  
## <a name="all-attributes"></a>Tutti gli attributi  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione di questo criterio da applicare ai tipi nell'applicazione. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato assembly.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato spazio dei nomi.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri a un determinato tipo, ad esempio una classe o una struttura.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Applica i criteri a un tipo generico costruito. Ad esempio, un elemento [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) può essere usato per definire i criteri per un tipo `List<String>`.|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Applica criteri a un metodo su un particolare tipo.|  
|[\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Applica i criteri a un metodo generico costruito.|  
|[\<Property>](../../../docs/framework/net-native/property-element-net-native.md)|Applica criteri a una proprietà su un particolare tipo.|  
|[\<Field>](../../../docs/framework/net-native/field-element-net-native.md)|Applica criteri a un campo su un particolare tipo.|  
|[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|Applica criteri a un evento su un particolare tipo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|L'elemento radice di un file di direttive di runtime.|  
  
## <a name="remarks"></a>Note  
 L'elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) può contenere nessuno o un elemento `<Application>`. Non sono supportati più elementi `<Application>` in un solo file di direttive di reflection.  
  
 L'elemento `<Application>` può essere usato in uno dei due modi seguenti:  
  
-   Come contenitore per definire gli elementi di programma i cui metadati sono necessari in fase di esecuzione. In tal caso, l'elemento `<Application>` non deve avere alcun attributo. Durante la compilazione, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio dell'elemento `<Application>` in tutte le librerie, incluse le librerie di base .NET Framework. Al contrario, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio di [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) solo nella libreria designata dall'elemento [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
-   Come elemento che imposta i criteri a livello di applicazione per la reflection, la serializzazione e l'interoperabilità. Gli attributi dell'elemento `<Application>` definiscono i criteri a livello di applicazione, che possono essere sottoposti a override da elementi figlio definiti dall'elemento `<Application>` o [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
## <a name="see-also"></a>Vedere anche  
 [\<Libreria > elemento](../../../docs/framework/net-native/library-element-net-native.md)  
 [\<Direttive > elemento](../../../docs/framework/net-native/directives-element-net-native.md)  
 [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
