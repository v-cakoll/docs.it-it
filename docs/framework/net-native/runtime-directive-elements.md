---
title: Elementi direttiva di runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128175"
---
# <a name="runtime-directive-elements"></a>Elementi direttiva di runtime
Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime. Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](application-element-net-native.md)  
 Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione. Si tratta di un elemento figlio dell' [\<Directives>](directives-element-net-native.md) elemento.  
  
 [\<Assembly>](assembly-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Si tratta di un elemento figlio [\<Application>](application-element-net-native.md) degli [\<Library>](library-element-net-native.md) elementi e.  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 Se la [\<Type>](type-element-net-native.md) direttiva contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.  
  
 [\<Directives>](directives-element-net-native.md)  
 Elemento radice in ogni file di direttive di runtime per .NET Native. I relativi elementi figlio sono [\<Application>](application-element-net-native.md) e [\<Library>](library-element-net-native.md) .  
  
 [\<Event>](event-element-net-native.md)  
 Applica criteri di runtime a un evento. Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.  
  
 [\<Field>](field-element-net-native.md)  
 Applica criteri di runtime a un campo. Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.  
  
 [\<Library>](library-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Si tratta di un elemento figlio [\<Application>](application-element-net-native.md) degli [\<Library>](library-element-net-native.md) elementi e.  
  
 [\<Method>](method-element-net-native.md)  
 Applica criteri di runtime a un metodo. Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 Applica criteri di runtime a un metodo generico costruito. Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.  
  
 [\<Namespace>](namespace-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.  
  
 [\<Parameter>](parameter-element-net-native.md)  
 Applica criteri di runtime al tipo di argomento passato a un metodo.  
  
 [\<Property>](property-element-net-native.md)  
 Applica criteri di runtime a una proprietà. Si tratta di un elemento figlio [\<Type>](type-element-net-native.md) degli [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elementi e.  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.  
  
 [\<Type>](type-element-net-native.md)  
 Applica criteri di runtime a un tipo.  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 Applica criteri di runtime a un tipo generico costruito.  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.  
  
## <a name="see-also"></a>Vedi anche

- [Informazioni di riferimento sul file di configurazione rd.xml](runtime-directives-rd-xml-configuration-file-reference.md)
