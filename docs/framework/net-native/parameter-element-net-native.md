---
title: <Parameter>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c9a462e75df535504d0e98c22c34c11ff7af7d8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049343"
---
# <a name="parameter-element-net-native"></a>\<Elemento > parametro (.NET Native)
Applica criteri di reflection al tipo di argomento passato a un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Nome del parametro. Ad esempio, per la firma del metodo `String.CompareTo(Object value)`, il valore dell'attributo `Name` è "value".|  
|`Activate`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione ai costruttori per abilitare l'attivazione di istanze.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla le query per le informazioni sugli elementi di programma, ma non abilita l'accesso in fase di esecuzione.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a tutti i membri dei tipi, inclusi costruttori, metodi, campi, proprietà ed eventi, per abilitare la programmazione dinamica.|  
|`Serialize`|Serializzazione|Attributo facoltativo. Controlla l'accesso in fase di esecuzione a costruttori, campi e proprietà per abilitare la serializzazione e la deserializzazione delle istanze del tipo da parte di librerie quali il serializzatore JSON di Newtonsoft.|  
|`DataContractSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione JSON che usano la classe <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serializzazione|Attributo facoltativo. Controlla i criteri per la serializzazione XML che usano la classe <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interoperabilità|Attributo facoltativo. Criteri di controlli per effettuare il marshalling dei tipi di riferimento per WinRT e COM.|  
|`MarshalDelegate`|Interoperabilità|Attributo facoltativo. Controlla i criteri per effettuare il marshalling dei tipi delegati come puntatori a funzioni al codice nativo.|  
|`MarshalStructure`|Interoperabilità|Attributo facoltativo. Controlla i criteri per il marshalling dei tipi di valore al codice nativo.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*parameter_name*|Il nome del parametro del metodo a cui è applicato il criterio. Ad esempio, per la firma del metodo `String.CompareTo(Object value)`, il valore dell'attributo `Name` è "value".|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri. I valori consentiti sono `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` e `Required All`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|Applica i criteri di reflection di runtime a un costruttore o a un metodo.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<Parameter>` è figlio dell'elemento [\<Method>](method-element-net-native.md) e viene usato per applicare criteri a un parametro di metodo specifico. Il parametro del metodo specifico viene specificato per nome anziché in base al tipo. Almeno un attributo che rappresenta un tipo di criterio, ad esempio `Activate` o `Dynamic`, deve essere presente.  
  
## <a name="see-also"></a>Vedere anche

- [Elemento \<Method>](method-element-net-native.md)
- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Impostazioni dei criteri delle direttive di runtime](runtime-directive-policy-settings.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
