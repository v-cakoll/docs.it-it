---
title: <Directives>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202375"
---
# <a name="directives-element-net-native"></a>\<Directives>Elemento (.NET Native)
Elemento radice in ogni file di direttive di runtime per .NET Native.  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`xmlns`|Spazio dei nomi XML. Il valore è sempre `http://schemas.microsoft.com/netfx/2013/01/metadata` .|  
  
## <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.|  
|[\<Library>](library-element-net-native.md)|Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.|  
  
## <a name="remarks"></a>Commenti  
 Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.  
  
 L' `<Directives>` elemento può contenere zero o un [\<Application>](application-element-net-native.md) elemento e zero, uno o più [\<Library>](library-element-net-native.md) elementi.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
