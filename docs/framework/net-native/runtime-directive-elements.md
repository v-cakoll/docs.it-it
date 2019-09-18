---
title: Elementi direttiva di runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 062f13ad92f37bb7ae29ed34dcf88f99f98e7612
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049262"
---
# <a name="runtime-directive-elements"></a>Elementi direttiva di runtime
Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime. Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](application-element-net-native.md)  
 Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione. Questo è un elemento figlio dell'elemento [\<Directives>](directives-element-net-native.md).  
  
 [\<Assembly>](assembly-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Questo è un elemento figlio degli elementi [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 Se la direttiva [\<Type>](type-element-net-native.md) contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.  
  
 [\<Directives>](directives-element-net-native.md)  
 Elemento radice in ogni file di direttive di runtime per .NET Native. I relativi elementi figlio sono [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).  
  
 [\<Event>](event-element-net-native.md)  
 Applica criteri di runtime a un evento. Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Field>](field-element-net-native.md)  
 Applica criteri di runtime a un campo. Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.  
  
 [\<Library>](library-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Questo è un elemento figlio degli elementi [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md).  
  
 [\<Method>](method-element-net-native.md)  
 Applica criteri di runtime a un metodo. Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 Applica criteri di runtime a un metodo generico costruito. Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Namespace>](namespace-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.  
  
 [\<Parameter>](parameter-element-net-native.md)  
 Applica criteri di runtime al tipo di argomento passato a un metodo.  
  
 [\<Property>](property-element-net-native.md)  
 Applica criteri di runtime a una proprietà. Questo è un elemento figlio degli elementi [\<Type>](type-element-net-native.md) e [\<TypeInstantiation>](typeinstantiation-element-net-native.md).  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.  
  
 [\<Type>](type-element-net-native.md)  
 Applica criteri di runtime a un tipo.  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 Applica criteri di runtime a un tipo generico costruito.  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione rd.xml](runtime-directives-rd-xml-configuration-file-reference.md)
