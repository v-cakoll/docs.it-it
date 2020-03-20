---
title: <Directives>Elemento (.NET native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181051"
---
# <a name="directives-element-net-native"></a>\<Direttive>elemento (.NET native)Directives (.NET Native)
Elemento radice in ogni file di direttive di runtime per .NET Native.The root element in every runtime directives file for .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`xmlns`|Spazio dei nomi XML. Il suo valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata" .**|  
  
## <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>dell'applicazione](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.|  
|[\<>libreria](library-element-net-native.md)|Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.  
  
 L'elemento `<Directives>` può contenere zero o un [ \<elemento Application>](application-element-net-native.md) e zero, uno o più [ \<](library-element-net-native.md) elementi Library>.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
