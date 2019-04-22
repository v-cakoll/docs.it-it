---
title: <Property> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20657e0a583890b851ab8e15c50bce791a3641b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094489"
---
# <a name="property-element-net-native"></a>\<Proprietà > elemento (.NET Native)
Applica i criteri di reflection di runtime a una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome della proprietà.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni o per l'enumerazione della proprietà, ma non abilita l'accesso dinamico al runtime.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione alla proprietà per abilitare la programmazione dinamica. Questo criterio assicura che una proprietà può essere impostata o recuperata dinamicamente in fase di esecuzione.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a una proprietà per abilitare le istanze di tipo da serializzare in librerie quali il serializzatore JSON Newtonsoft o da usare per il data binding.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*method_name*|Nome della proprietà. Il tipo di proprietà viene definito dall'elemento padre [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per la proprietà. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Note  
 Se i criteri di una proprietà non sono definiti esplicitamente, la proprietà eredita i criteri di runtime dell'elemento padre.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si usa la reflection per creare un'istanza di un oggetto `Book` e visualizzare i valori delle proprietà. Il file originale default.rd.xml per il progetto viene visualizzato come segue:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 Il file applica il valore `All` ai criteri `Activate` per la classe `Book`, che consente di accedere ai costruttori della classe tramite la reflection. I criteri `Browse` per la classe `Book` vengono ereditati dal relativo spazio dei nomi padre. Questa proprietà è impostata su `Required Public`, che rende disponibili i metadati in fase di esecuzione.  
  
 Di seguito viene riportato il codice sorgente per l'esempio. Il `outputBlock` variabile rappresenta un <xref:Windows.UI.Xaml.Controls.TextBlock> controllo.  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 Tuttavia, la compilazione e l'esecuzione di questo esempio genera un'eccezione [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md). Anche se i metadati per il tipo `Book` sono stati resi disponibili, non è stato possibile rendere disponibili le implementazioni di funzioni Get di proprietà in modo dinamico. È possibile correggere l'errore in uno di due modi:  
  
-   Definendo i criteri `Dynamic` per il tipo `Book` nel relativo elemento [\<Type>](../../../docs/framework/net-native/type-element-net-native.md).  
  
-   Aggiungendo un elemento [\<Property>](../../../docs/framework/net-native/property-element-net-native.md) annidato per ogni proprietà per cui si intende richiamare il getter, come nel seguente file default.rd.xml.  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Impostazioni dei criteri delle direttive di runtime](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
