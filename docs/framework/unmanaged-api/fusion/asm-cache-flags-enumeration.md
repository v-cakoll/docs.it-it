---
title: Enumerazione ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 619643eb50abc75fd10d59b38767013b2617c8cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077777"
---
# <a name="asmcacheflags-enumeration"></a>Enumerazione ASM_CACHE_FLAGS
Indica l'origine di un assembly rappresentato da [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) nella global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Enumera la cache di assembly precompilati usando Ngen.exe.|  
|`ASM_CACHE_GAC`|Enumera la global assembly cache.|  
|`ASM_CACHE_DOWNLOAD`|Enumera gli assembly che sono stati scaricati su richiesta o che sono stati replicati.|  
|`ASM_CACHE_ROOT`|Indica che il [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funzione deve restituire il percorso alla global assembly cache per common language runtime (CLR) versione 2.0. Significativo solo nel contesto di una chiamata a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Indica che il [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funzione deve restituire il percorso alla global assembly cache per la versione 4 di CLR. Significativo solo nel contesto di una chiamata a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [Interfaccia IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [Enumerazioni Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
