---
title: Elemento <MethodInstantiation> (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
ms.openlocfilehash: f19bd3c20088431bcbbafac298398b82a664bee9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128331"
---
# <a name="methodinstantiation-element-net-native"></a>\<elemento MethodInstantiation > (.NET Native)
Applica i criteri di reflection di runtime a un metodo generico costruito.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Tipo di attributo|Descrizione|  
|---------------|--------------------|-----------------|  
|`Name`|Generale|Attributo obbligatorio. Specifica il nome del metodo.|  
|`Signature`|Generale|Attributo facoltativo. Specifica i parametri denominati del metodo. Più parametri denominati sono separati da virgole. L'attributo `Signature` viene usato per differenziare i metodi sottoposti a overload.|  
|`Arguments`|Generale|Attributo obbligatorio. Specifica gli argomenti tipo generico. Se sono presenti più argomenti, saranno separati da virgole.|  
|`Browse`|Reflection|Attributo facoltativo. Controlla l'esecuzione di query per informazioni sul metodo o la sua enumerazione, ma non abilita alcuna chiamata dinamica in fase di esecuzione.|  
|`Dynamic`|Reflection|Attributo facoltativo. Controlla l'accesso del runtime a un costruttore o al metodo per attivare la programmazione dinamica. Questo criterio assicura che un membro possa essere richiamato in modo dinamico in fase di esecuzione.|  
  
## <a name="name-attribute"></a>Name (attributo)  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*method_name*|Nome del metodo. Il tipo di metodo viene definito dall'elemento padre [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md).|  
  
## <a name="signature-attribute"></a>Attributo Signature  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*method_signature*|Specifica i parametri del metodo denominati. Se esistono più parametri, sono separati da virgole.|  
  
## <a name="arguments-attribute"></a>Attributo di argomenti  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*method_arguments*|Specifica gli argomenti tipo generico. Se sono presenti più argomenti, saranno separati da virgole. Ogni argomento deve essere costituito dal nome completo del tipo.|  
  
## <a name="all-other-attributes"></a>Tutti gli altri attributi  
  
|Value|Descrizione|  
|-----------|-----------------|  
|*policy_setting*|L'impostazione da applicare a questo tipo di criteri per il metodo. I valori consentiti sono `Auto`, `Excluded`, `Included` e `Required`. Per altre informazioni, vedere [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Impostazioni dei criteri delle direttive di runtime).|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Applica i criteri di reflection a un tipo e a tutti i membri.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Applica i criteri di reflection a un tipo generico costruito e a tutti i membri.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<MethodInstantiation>` prevale sui criteri di reflection di runtime del corrispondente metodo generico aperto.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
- [Impostazioni dei criteri delle direttive di runtime](runtime-directive-policy-settings.md)
- [Elemento \<Method>](method-element-net-native.md)
