---
title: <Assembly>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
ms.openlocfilehash: f3cf65b185b1db3289a0dbb785c2b91431951cc2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79181072"
---
# <a name="assembly-element-net-native"></a>\<Assembly>Elemento (.NET Native)
Applica i criteri di reflection di runtime a tutti i tipi in un determinato assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Assembly Name="assembly_name"
          Activate="policy_setting"  
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
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome semplice di un assembly.|  
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni o per l'enumerazione dei tipi nell'assembly, ma non abilita l'accesso dinamico al runtime.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|  
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.|  
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|  
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling delle strutture al codice nativo.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Valore|Description|  
|-----------|-----------------|  
|*assembly_name*|Il nome semplice dell'assembly, senza estensione di file. Questo attributo corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Ad esempio, il nome di un assembly denominato Extensions.dll è "Extensions".<br /><br /> È anche possibile specificare la stringa letterale `*Application*` per applicare i criteri a tutti gli assembly nel pacchetto dell'app, a prescindere se siano caricati o meno. `*Application*` non applica mai i criteri agli assembly di .NET Framework.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Valore|Description|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per tutti i tipi nell'assembly. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Namespace>](namespace-element-net-native.md)|Applica i criteri di reflection a tutti i tipi in uno spazio dei nomi figlio.|  
|[\<Type>](type-element-net-native.md)|Applica i criteri di reflection a un tipo.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection al runtime. L' [\<Application>](application-element-net-native.md) elemento può contenere zero, uno o più `<Assembly>` elementi.|  
|[\<Library>](library-element-net-native.md)|Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime. L' [\<Library>](library-element-net-native.md) elemento può contenere zero o un `<Assembly>` elemento.|  
  
## <a name="remarks"></a>Commenti  
 L'elemento `<Assembly>` definisce i criteri di runtime per tutti i tipi in un assembly. È diverso dall' [\<Library>](library-element-net-native.md) elemento, che specifica una libreria, ma dipende dagli elementi figlio per definire i criteri di reflection di Runtime. L'elemento `<Assembly>` si applica a tutti i tipi in un assembly a meno che questi non siano sottoposti a override da un elemento figlio.  
  
 L'esempio seguente illustra come applicare i criteri di runtime a tutti i tipi presenti negli assembly all'interno del pacchetto di app assegnando un valore "*Application\*" all'attributo `Name`. L' `<Assembly>` elemento deve essere un elemento figlio dell' [\<Application>](application-element-net-native.md) elemento.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>  
```  
  
 Gli attributi `Activate`, `Browse`, `Dynamic` e `Serialize` sono tutti facoltativi. Tuttavia, l'elemento `<Assembly>` deve contenere almeno uno di questi attributi.  
  
## <a name="see-also"></a>Vedi anche

- [Impostazioni dei criteri della direttiva di runtime](runtime-directive-policy-settings.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
