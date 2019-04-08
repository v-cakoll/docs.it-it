---
title: <Library> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda4f8d3819af05b022e0633d6883cca940f67e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100262"
---
# <a name="library-element-net-native"></a>\<Libreria > elemento (.NET Native)
Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime.  
  
 Elemento \<Directives>  
Elemento \<Library>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`Name`|Attributo obbligatorio. Specifica il nome di un assembly. Gli elementi figlio di questo elemento `<Library>` definiscono i criteri di reflection di runtime per i tipi e i membri dei tipi rilevati nell'assembly.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*assembly_name*|Il nome semplice dell'assembly, senza estensione di file. Questo attributo corrisponde alla proprietà <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Ad esempio, il nome di un assembly denominato Extensions.dll è "Extensions". Vedere la sezione Note per informazioni su un formato speciale di *assembly_name* che supporta l'inclusione condizionale di metadati dall'assembly.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato assembly.|  
|[\<Namespace >](../../../docs/framework/net-native/namespace-element-net-native.md)|Applica i criteri a tutti i tipi in un determinato spazio dei nomi.|  
|[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri a un determinato tipo, ad esempio una classe o una struttura.|  
|[\<TypeInstantiation >](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Applica i criteri a un tipo generico costruito. Ad esempio, un elemento [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) può essere usato per definire i criteri per un tipo `List<String>`.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Direttive >](../../../docs/framework/net-native/directives-element-net-native.md)|L'elemento radice di un file di direttive di runtime.|  
  
## <a name="remarks"></a>Note  
 L'elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) può contenere nessuno, uno o più elementi `<Library>`.  
  
 L'elemento `<Library>` viene usato come contenitore per definire gli elementi di programma i cui metadati sono richiesti al runtime; questo elemento non esprime criteri. Durante la compilazione, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio solo nella libreria designata dall'elemento `<Library>`. Al contrario, gli strumenti di compilazione cercano gli elementi di programma identificati dagli elementi figlio dell'elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) in tutte le librerie, incluse le librerie di base .NET Framework.  
  
 `<Library>` direttive possono essere usate in modo condizionale. Se il nome del `<Library>` elemento inizia e termina con un asterisco (\*), il `<Library>` direttiva ha effetto solo se viene fatto riferimento all'assembly racchiuso tra asterischi dall'app. Ad esempio, la seguente direttiva di runtime si applica solo se l'assembly Utillities.dll viene indicata dall'app.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>Vedere anche

- [\<Applicazione > elemento](../../../docs/framework/net-native/application-element-net-native.md)
- [Elemento \<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)
