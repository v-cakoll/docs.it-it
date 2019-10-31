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
ms.openlocfilehash: 85ac976daec8fd76ee21012a30611235609f4b34
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109485"
---
# <a name="asm_cache_flags-enumeration"></a>Enumerazione ASM_CACHE_FLAGS
Indica l'origine di un assembly rappresentato da [IAssemblyCacheItem](iassemblycacheitem-interface.md) nel Global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Enumera la cache degli assembly precompilati utilizzando Ngen. exe.|  
|`ASM_CACHE_GAC`|Enumera il Global Assembly Cache.|  
|`ASM_CACHE_DOWNLOAD`|Enumera gli assembly scaricati su richiesta o di cui è stata eseguita la copia shadow.|  
|`ASM_CACHE_ROOT`|Indica che la funzione [GetCachePath](getcachepath-function.md) deve restituire il percorso del Global assembly cache per la Common Language Runtime (CLR) versione 2,0. Significativo solo nel contesto di una chiamata a [GetCachePath](getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Indica che la funzione [GetCachePath](getcachepath-function.md) deve restituire il percorso del Global assembly cache per CLR versione 4. Significativo solo nel contesto di una chiamata a [GetCachePath](getcachepath-function.md).|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione GetCachePath](getcachepath-function.md)
- [Interfaccia IAssemblyCacheItem](iassemblycacheitem-interface.md)
- [Enumerazioni Fusion](fusion-enumerations.md)
