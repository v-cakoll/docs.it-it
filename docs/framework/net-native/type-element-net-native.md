---
title: <Type>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
ms.openlocfilehash: 4e88b49b82513079ddcf6f0bafe02d44235a406a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73091846"
---
# <a name="type-element-net-native"></a>\<Type>Elemento (.NET Native)

Applica i criteri di runtime a un determinato tipo, ad esempio una classe o una struttura.

## <a name="syntax"></a>Sintassi

```xml
<Type Name="type_name"
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
|`Name`|Generale|Attributo obbligatorio. Specifica il nome tipo.|
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.|
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi di riferimento a Windows Runtime e COM.|
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per il marshalling dei tipi di valore al codice nativo.|

## <a name="name-attribute"></a>Name (attributo)

|Valore|Description|
|-----------|-----------------|
|*type_name*|Nome del tipo. Se questo `<Type>` elemento è figlio di un [\<Namespace>](namespace-element-net-native.md) elemento o di un altro `<Type>` elemento, *type_name* possibile includere il nome del tipo senza il relativo spazio dei nomi. In caso contrario, *type_name* deve includere il nome completo del tipo.|

## <a name="all-other-attributes"></a>Tutti gli altri attributi

|Valore|Description|
|-----------|-----------------|
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri. I valori consentiti sono `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<AttributeImplies>](attributeimplies-element-net-native.md)|Se il tipo contenitore è un attributo, definisce i criteri di runtime per gli elementi del codice a cui è applicato l'attributo.|
|[\<Event>](event-element-net-native.md)|Applica i criteri di reflection a un evento appartenente a questo tipo.|
|[\<Field>](field-element-net-native.md)|Applica i criteri di reflection a un campo appartenente a questo tipo.|
|[\<GenericParameter>](genericparameter-element-net-native.md)|Applica i criteri al tipo di parametro di un tipo generico.|
|[\<ImpliesType>](impliestype-element-net-native.md)|Applica criteri a un tipo, se tale criterio è stato applicato al tipo rappresentato dall'oggetto contenente l'elemento `<Type>`.|
|[\<Method>](method-element-net-native.md)|Applica i criteri di reflection a un metodo appartenente a questo tipo.|
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Applica criteri di reflection a un metodo generico costruito, appartenente a questo tipo.|
|[\<Property>](property-element-net-native.md)|Applica i criteri di reflection a una proprietà appartenente a questo tipo.|
|[\<Subtypes>](subtypes-element-net-native.md)|Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.|
|`<Type>`|Applica criteri di reflection un tipo annidato.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<Application>](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection al runtime.|
|[\<Assembly>](assembly-element-net-native.md)|Applica i criteri di reflection a tutti i tipi in un determinato assembly.|
|[\<Library>](library-element-net-native.md)|Definisce l'assembly che contiene i tipi e i membri dei tipi i cui metadati sono disponibili per la reflection al runtime.|
|[\<Namespace>](namespace-element-net-native.md)|Applica criteri di reflection a tutti i tipi in uno spazio dei nomi.|
|`<Type>`|Applica i criteri di reflection a un tipo e a tutti i membri.|
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|

## <a name="remarks"></a>Commenti

La reflection, la serializzazione e gli attributi di interoperabilità sono facoltativi. Se non è presente, l'elemento `<Type>` funge da contenitore i cui tipi figlio definiscono criteri per i singoli membri.

Se un `<Type>` elemento è figlio di un [\<Assembly>](assembly-element-net-native.md) elemento, [\<Namespace>](namespace-element-net-native.md) , `<Type>` o [\<TypeInstantiation>](typeinstantiation-element-net-native.md) , sostituisce le impostazioni dei criteri definite dall'elemento padre.

Un elemento `<Type>` di un tipo generico applica i relativi criteri a tutte le istanze che non dispongono di propri criteri. Il criterio dei tipi generici costruiti viene definito dall' [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elemento.

Se il tipo è un tipo generico, il nome è decorato da un simbolo di accento grave ( \`) seguito dal relativo numero di parametri generici. Ad esempio, l'attributo `Name` di un elemento `<Type>` per la classe <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> viene visualizzato come ``Name="System.Collections.Generic.List`1"``.

## <a name="example"></a>Esempio

Nell'esempio seguente viene usata la reflection per visualizzare le informazioni su campi, proprietà e metodi della classe <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. La variabile `b` nell'esempio è un <xref:Windows.UI.Xaml.Controls.TextBlock> controllo. Poiché l'esempio recupera semplicemente le informazioni sul tipo, la disponibilità dei metadati è controllata dall'impostazione dei criteri `Browse`.

 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]

 Poiché i metadati per la <xref:System.Collections.Generic.List%601> classe non vengono inclusi automaticamente dalla catena di strumenti .NET native, l'esempio non riesce a visualizzare le informazioni sul membro richieste in fase di esecuzione. Per fornire i metadati necessari, aggiungere il seguente elemento `<Type>` al file di direttive di runtime. Da notare che dal momento che è stato fornito un elemento [<Namespace\>](namespace-element-net-native.md) padre, non è necessario fornire un nome di tipo completo nell'elemento `<Type>`.

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="*Application*" Dynamic="Required All" />
      <Namespace Name ="System.Collections.Generic" >
        <Type Name="List`1" Browse="Required All" />
     </Namespace>
   </Application>
</Directives>
```

## <a name="example"></a>Esempio
 Nell'esempio seguente viene usata la reflection per recuperare un oggetto <xref:System.Reflection.PropertyInfo> che rappresenta la proprietà <xref:System.String.Chars%2A?displayProperty=nameWithType>. Viene quindi usato il metodo <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> per recuperare il valore del settimo carattere in una stringa e visualizzare tutti i caratteri nella stringa. La variabile `b` nell'esempio è un <xref:Windows.UI.Xaml.Controls.TextBlock> controllo.

 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]

 Poiché i metadati per l' <xref:System.String> oggetto non sono disponibili, la chiamata al <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> metodo genera un' <xref:System.NullReferenceException> eccezione in fase di esecuzione quando viene compilata con la catena di strumenti .NET native. Per eliminare l'eccezione e fornire i metadati necessari, aggiungere il seguente elemento `<Type>` al file di direttive di runtime:

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Assembly Name="*Application*" Dynamic="Required All" />
    <Type Name="System.String" Dynamic="Required Public"/> -->
  </Application>
</Directives>
```

## <a name="see-also"></a>Vedi anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Impostazioni dei criteri della direttiva di runtime](runtime-directive-policy-settings.md)
