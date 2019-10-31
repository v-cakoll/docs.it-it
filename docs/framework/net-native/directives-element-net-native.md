---
title: Elemento <Directives> (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: abe2e7221e0afb984a6178b12fabc36ea24deb35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128464"
---
# <a name="directives-element-net-native"></a>Elemento > \<direttive (.NET Native)
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
|`xmlns`|Spazio dei nomi XML. Il valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"** .|  
  
## <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.|  
|[\<Library>](library-element-net-native.md)|Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.  
  
 L'elemento `<Directives>` può contenere zero o un elemento [\<Application>](application-element-net-native.md) e zero, uno o più elementi [\<Library>](library-element-net-native.md).  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](runtime-directive-elements.md)
