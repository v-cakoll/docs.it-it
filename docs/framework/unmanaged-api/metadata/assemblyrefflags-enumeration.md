---
title: Enumerazione AssemblyRefFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyRefFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyRefFlags
helpviewer_keywords: AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc64d03725df89eac91c85549e287eeb2510037c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyrefflags-enumeration"></a>Enumerazione AssemblyRefFlags
Contiene valori che descrivono le funzionalità di un riferimento all'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`arfFullOriginator`|Specifica che il riferimento all'assembly contiene completa, senza hash informazioni sull'autore dell'assembly.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [DefineAssemblyRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
