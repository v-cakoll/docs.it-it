---
title: <Method>Elemento (.NET native)
ms.date: 03/30/2017
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
ms.openlocfilehash: 8db32c660846b4f4071fff2a40c760a3d1ef2489
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180979"
---
# <a name="method-element-net-native"></a>\<Elemento> metodo (.NET native)Method> Element (.NET Native)
Applica i criteri di reflection di runtime a un costruttore o a un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome del metodo.|  
|`Signature`|Generale|Attributo facoltativo. Specifica la firma del metodo. Se esistono più parametri, sono separati da virgole. Ad esempio, l'elemento `<Method>` seguente definire i criteri del metodo <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29>.<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> Se l'attributo è assente, la direttiva di runtime si applica a tutti gli overload del metodo.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla l'esecuzione di query per informazioni sul metodo o la sua enumerazione, ma non abilita alcuna chiamata dinamica in fase di esecuzione.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso del runtime a un costruttore o al metodo per attivare la programmazione dinamica. Questo criterio assicura che un membro possa essere richiamato in modo dinamico in fase di esecuzione.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|valore|Descrizione|  
|-----------|-----------------|  
|*method_name*|Nome del metodo. Il tipo del metodo è definito dall'elemento [ \<di>](type-element-net-native.md) [ \<Type](typeinstantiation-element-net-native.md)>o TypeInstantiation padre.|  
  
## <a name="signature-attribute"></a>Attributo Signature  
  
|valore|Descrizione|  
|-----------|-----------------|  
|*method_signature*|Tipi di parametri che costituiscono la firma del metodo. Più parametri sono separati da virgole, ad esempio `"System.String,System.Int32,System.Int32)"`. I nomi del tipo di parametro devono essere completi.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|valore|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>dei parametri](parameter-element-net-native.md)|Applica i criteri al tipo di argomento passato a un metodo.|  
|[\<GenericParameter>](genericparameter-element-net-native.md)|Applica i criteri al tipo di parametro di un tipo o di un metodo generico.|  
|[\<>ImpliesType](impliestype-element-net-native.md)|Applica criteri a un tipo, se tale criterio è stato applicato al metodo rappresentato dall'oggetto contenente l'elemento `<Method>`.|  
|[\<>TypeParameter](typeparameter-element-net-native.md)|Applica i criteri al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Tipo>](type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<>TypeInstantiation](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Osservazioni  
 Un elemento `<Method>` di un metodo generico applica i relativi criteri a tutte le istanze che non dispongono di propri criteri.  
  
 È possibile usare l'attributo `Signature` per specificare criteri per un overload del metodo specifico. In caso contrario, se l'attributo `Signature` è assente, la direttiva di runtime si applica a tutti gli overload del metodo.  
  
 Non è possibile definire i criteri di reflection di runtime per un costruttore con l'elemento `<Method>`. Utilizzare invece `Activate` l'attributo dell'elemento [ \<>Assembly ](assembly-element-net-native.md), [ \<Namespace>](namespace-element-net-native.md), [ \<Type>](type-element-net-native.md)o [ \<TypeInstantiation>.](typeinstantiation-element-net-native.md)  
  
## <a name="example"></a>Esempio  
 Il metodo `Stringify` nell'esempio seguente è un metodo di formattazione generico che usa la reflection per convertire un oggetto nella relativa rappresentazione di stringa. Oltre a chiamare il metodo `ToString` predefinito dell'oggetto, il metodo può produrre una stringa di risultato formattata passando il metodo `ToString` di un oggetto a una stringa di formato, un'implementazione di <xref:System.IFormatProvider> o entrambi. Il metodo può anche chiamare uno degli overload <xref:System.Convert.ToString%2A?displayProperty=nameWithType> che converte un numero nella relativa rappresentazione binaria, ottale o esadecimale.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Il metodo `Stringify` può essere chiamato da codice simile al seguente:  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Tuttavia, quando viene compilato con .NET Native, l'esempio può generare una serie di eccezioni in fase di esecuzione, incluse le eccezioni <xref:System.NullReferenceException> e [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Ciò si verifica perché il metodo `Stringify` è destinato principalmente a supportare la formattazione dinamica dei tipi primitivi nella libreria di classi .NET Framework. Tuttavia, i metadati non vengono resi disponibili dal file di direttive predefinito. Anche quando i metadati vengono resi disponibili, tuttavia, l'esempio genererà le eccezioni [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) perché le implementazioni `ToString` appropriate non sono state incluse nel codice nativo.  
  
 Queste eccezioni possono essere eliminate [ \<](type-element-net-native.md) utilizzando il Type>elemento per definire i `<Method>` tipi i cui metadati devono essere presenti e aggiungendo elementi per garantire che sia presente anche l'implementazione di overload del metodo che possono essere chiamati in modo dinamico. Di seguito è riportato il file default.rd.xml che elimina queste eccezioni e consente l'esecuzione dell'esempio senza errori.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime)
- [\<Elemento> MethodInstantiation](methodinstantiation-element-net-native.md)
