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
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150982"
---
# <a name="getcachepath-function"></a>Funzione GetCachePath
Ottiene il percorso all'assembly memorizzati nella cache, usando i flag specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `dwCacheFlags`  
 [in] Un' [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) valore che indica l'origine dell'assembly memorizzati nella cache.  
  
 `pwzCachePath`  
 [out] Il puntatore restituito al percorso.  
  
 `pcchPath`  
 [in, out] La lunghezza massima richiesta del `pwzCachePath`e dopo la restituzione, la lunghezza effettiva dei `pwzCachePath`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazione ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
