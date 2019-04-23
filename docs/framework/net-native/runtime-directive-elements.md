---
title: Elementi direttiva di runtime
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf692ff93a575858d1d1a89346611cb9c5957b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137813"
---
# <a name="runtime-directive-elements"></a>Elementi direttiva di runtime
Il formato del file delle direttive di runtime (rd.xml) supporta i seguenti elementi direttiva di runtime. Per una rappresentazione gerarchica, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)  
 Applica criteri di reflection di runtime a tutti i tipi usati dall'app e funge da contenitore per i tipi a livello di applicazione e i membri del tipo i cui metadati sono disponibili per la reflection in fase di esecuzione. Questo è un elemento figlio dell'elemento [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md).  
  
 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Questo è un elemento figlio degli elementi [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
 [\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 Se la direttiva [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) contenitore è un attributo, applica i criteri di runtime agli elementi di codice a cui è applicato l'attributo.  
  
 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)  
 Elemento radice in ogni file di direttive di runtime per [!INCLUDE[net_native](../../../includes/net-native-md.md)]. I relativi elementi figlio sono [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
 [\<Event>](../../../docs/framework/net-native/event-element-net-native.md)  
 Applica criteri di runtime a un evento. Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
 [\<Field>](../../../docs/framework/net-native/field-element-net-native.md)  
 Applica criteri di runtime a un campo. Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
 [\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 Applica i criteri di runtime al tipo di parametro di un tipo o di un metodo generico.  
  
 [\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 Applica criteri di runtime a un tipo, se tale criterio è stato applicato al metodo o al tipo contenitore.  
  
 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in un assembly. Questo è un elemento figlio degli elementi [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)  
 Applica criteri di runtime a un metodo. Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
 [\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 Applica criteri di runtime a un metodo generico costruito. Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
 [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 Applica criteri di runtime a tutti i tipi in uno spazio dei nomi.  
  
 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 Applica criteri di runtime al tipo di argomento passato a un metodo.  
  
 [\<Property>](../../../docs/framework/net-native/property-element-net-native.md)  
 Applica criteri di runtime a una proprietà. Questo è un elemento figlio degli elementi [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) e [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).  
  
 [\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 Applica i criteri di runtime a tutte le classi ereditate per il tipo contenitore.  
  
 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)  
 Applica criteri di runtime a un tipo.  
  
 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 Applica criteri di runtime a un tipo generico costruito.  
  
 [\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 Applica criteri di runtime al tipo rappresentato da un argomento <xref:System.Type> passato a un metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione rd.xml](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
