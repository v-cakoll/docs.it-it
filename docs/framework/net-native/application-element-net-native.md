---
title: <Application>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
ms.openlocfilehash: e26826b3d8674b536ab0897182da58bc02cfd00b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128523"
---
# <a name="application-element-net-native"></a>\<Application>Elemento (.NET Native)
Funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione e applica criteri di reflection di runtime a tutti gli elementi del programma in un'applicazione.  
  
 \<Directives> Elemento  
\<Application>Elemento (Rd. Xml)  
  
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
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling delle strutture al codice nativo.|  
  
## <a name="all-attributes"></a>Tutti gli attributi  
  
|Valore|Description|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione di questo criterio da applicare ai tipi nell'applicazione. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Assembly>](assembly-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato assembly.|  
|[\<Namespace>](namespace-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato spazio dei nomi.|  
|[\<Type>](type-element-net-native.md)|Applica i criteri a un determinato tipo, ad esempio una classe o una struttura.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri a un tipo generico costruito. Ad esempio, [\<TypeInstantiation>](typeinstantiation-element-net-native.md) è possibile usare un elemento per definire i criteri per un `List<String>` tipo.|  
|[\<Method>](method-element-net-native.md)|Applica criteri a un metodo su un particolare tipo.|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Applica i criteri a un metodo generico costruito.|  
|[\<Property>](property-element-net-native.md)|Applica criteri a una proprietà su un particolare tipo.|  
|[\<Field>](field-element-net-native.md)|Applica criteri a un campo su un particolare tipo.|  
|[\<Event>](event-element-net-native.md)|Applica criteri a un evento su un particolare tipo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Directives>](directives-element-net-native.md)|L'elemento radice di un file di direttive di runtime.|  
  
## <a name="remarks"></a>Commenti  
 L' [\<Directives>](directives-element-net-native.md) elemento può contenere zero o un `<Application>` elemento. Non sono supportati più elementi `<Application>` in un solo file di direttive di reflection.  
  
 L'elemento `<Application>` può essere usato in uno dei due modi seguenti:  
  
- Come contenitore per definire gli elementi di programma i cui metadati sono necessari in fase di esecuzione. In tal caso, l'elemento `<Application>` non deve avere alcun attributo. Durante la compilazione, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio dell'elemento `<Application>` in tutte le librerie, incluse le librerie di base .NET Framework. Al contrario, gli strumenti di compilazione cercano solo la libreria designata dall' [\<Library>](library-element-net-native.md) elemento per gli elementi di programma identificati dagli elementi figlio di [\<Library>](library-element-net-native.md) .  
  
- Come elemento che imposta i criteri a livello di applicazione per la reflection, la serializzazione e l'interoperabilità. Gli attributi dell' `<Application>` elemento definiscono i criteri a livello di applicazione, che possono essere sottoposti a override dagli elementi figlio definiti `<Application>` dall' [\<Library>](library-element-net-native.md) elemento o.  
  
## <a name="see-also"></a>Vedi anche

- [\<Library>Elemento](library-element-net-native.md)
- [\<Directives>Elemento](directives-element-net-native.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
