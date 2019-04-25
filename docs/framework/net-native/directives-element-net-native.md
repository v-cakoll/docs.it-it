---
title: <Directives> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868586"
---
# <a name="directives-element-net-native"></a>\<Direttive > elemento (.NET Native)
L'elemento radice in ogni file di direttive di runtime per .NET Native.  
  
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
|`xmlns`|Spazio dei nomi XML. Il valore è sempre **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.|  
  
## <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Viene usato come contenitore per i tipi e i membri dei tipi a livello di applicazione i cui metadati sono disponibili per la reflection.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Definisce l'assembly i cui tipi di figlio e i membri di tipo richiedono metadati in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Ogni file di direttive di runtime può contenere un solo elemento `<Directives>`.  
  
 L'elemento `<Directives>` può contenere zero o un elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) e zero, uno o più elementi [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementi direttiva di runtime](../../../docs/framework/net-native/runtime-directive-elements.md)
