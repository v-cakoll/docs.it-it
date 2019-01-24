---
title: Elemento &lt;TypeInstantiation&gt; (.NET Native)
ms.date: 03/30/2017
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 818a52ceb1428327c5bcb778f85015458990578f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612563"
---
# <a name="lttypeinstantiationgt-element-net-native"></a>Elemento &lt;TypeInstantiation&gt; (.NET Native)
Applica i criteri di reflection di runtime a un tipo generico costruito.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
                   Activate="policy_type"  
                   Browse="policy_type"  
                   Dynamic="policy_type"  
                   Serialize="policy_type"  
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
|`Name`|Generale|Attributo obbligatorio. Specifica il nome del tipo.|  
|`Arguments`|Generale|Attributo obbligatorio. Specifica gli argomenti di tipo generico. Se sono presenti più argomenti, saranno separati da virgole.|  
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|  
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.|  
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|  
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per il marshalling delle strutture al codice nativo.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*type_name*|Nome del tipo. Se questo elemento `<TypeInstantiation>` è figlio di un elemento [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md), un elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o di un altro elemento `<TypeInstantiation>`, *type_name* può specificare il nome del tipo senza il relativo spazio dei nomi. In caso contrario, *type_name* deve includere il nome completo del tipo. Il nome del tipo non è decorato. Ad esempio, per un oggetto <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, l'elemento `<TypeInstantiation>` può apparire come segue:<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>Attributo di argomenti  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*type_argument*|Specifica gli argomenti tipo generico. Se sono presenti più argomenti, saranno separati da virgole. Ogni argomento deve essere costituito dal nome completo del tipo.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per il tipo generico costruito. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|Applica i criteri di reflection a un evento appartenente a questo tipo.|  
|[\<Field>](../../../docs/framework/net-native/field-element-net-native.md)|Applica i criteri di reflection a un campo appartenente a questo tipo.|  
|[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Applica criteri a un tipo, se tale criterio è stato applicato al tipo rappresentato dall'oggetto contenente l'elemento `<TypeInstantiation>`.|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Applica i criteri di reflection a un metodo appartenente a questo tipo.|  
|[\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Applica criteri di reflection a un metodo generico costruito, appartenente a questo tipo.|  
|[\<Property>](../../../docs/framework/net-native/property-element-net-native.md)|Applica i criteri di reflection a una proprietà appartenente a questo tipo.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica criteri di reflection un tipo annidato.|  
|`<TypeInstantiation>`|Applica i criteri di reflection a un tipo generico costruito annidato.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection al runtime.|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Applica i criteri di reflection a tutti i tipi in un determinato assembly.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Applica criteri di reflection a tutti i tipi in uno spazio dei nomi.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|`<TypeInstantiation>`|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Note  
 La reflection, la serializzazione e gli attributi di interoperabilità sono facoltativi. ma è necessario usarne almeno uno.  
  
 Se un elemento `<TypeInstantiation>` è figlio di un elemento [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md), [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md) o [\<Type>](../../../docs/framework/net-native/type-element-net-native.md), sottopone a override le impostazioni dei criteri definite dall'elemento padre. Se un elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) definisce una corrispondente definizione di tipo generico, l'elemento `<TypeInstantiation>` esegue l'override dei criteri di reflection di runtime solo per le istanze del tipo generico costruito specificato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usata la reflection per recuperare la definizione di tipo generico da un oggetto <xref:System.Collections.Generic.Dictionary%602> costruito. Viene anche usata la reflection per visualizzare informazioni sugli oggetti <xref:System.Type> che rappresentano tipi generici costruiti e definizioni di tipo generico. La variabile `b` nell'esempio è un <xref:Windows.UI.Xaml.Controls.TextBlock> controllo.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 Dopo aver eseguito la compilazione con la catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)], l'esempio genera un'eccezione [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) sulla riga che chiama il metodo <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType>. È possibile eliminare l'eccezione e fornire i metadati necessari aggiungendo il seguente elemento `<TypeInstantiation>` al file di direttive di runtime:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Impostazioni dei criteri delle direttive di runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
