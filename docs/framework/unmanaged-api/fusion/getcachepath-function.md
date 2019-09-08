---
title: Funzione GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796901"
---
# <a name="getcachepath-function"></a>Funzione GetCachePath
Ottiene il percorso dell'assembly memorizzato nella cache, usando i flag specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `dwCacheFlags`  
 in Valore [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) che indica l'origine dell'assembly memorizzato nella cache.  
  
 `pwzCachePath`  
 out Puntatore restituito al percorso.  
  
 `pcchPath`  
 [in, out] Lunghezza massima richiesta di `pwzCachePath`e, al momento della restituzione, la lunghezza effettiva di. `pwzCachePath`  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
