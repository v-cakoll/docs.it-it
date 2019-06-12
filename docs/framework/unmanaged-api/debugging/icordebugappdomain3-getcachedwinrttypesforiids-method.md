---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95c84f7f40db0096b26ec448f8f229cdbfe3afb1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025898"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Ottiene un enumeratore per i tipi Windows Runtime memorizzato nella cache in un dominio di applicazione basato su identificatori relativi interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cReqTypes`  
 [in] Il numero di tipi richiesti.  
  
 `iidsToResolve`  
 [in] Puntatore a una matrice contenente gli identificatori di interfaccia corrispondenti per le rappresentazioni gestite dei tipi Windows Runtime da recuperare.  
  
 `ppTypesEnum`  
 [out] Un puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugTypeEnum" che consente l'enumerazione delle rappresentazioni gestite memorizzato nella cache dei tipi Windows Runtime recuperati in base gli identificatori di interfaccia in `iidsToResolve`.  
  
## <a name="remarks"></a>Note  
 Se il metodo non riesce a recuperare le informazioni per un identificatore di interfaccia specifica, la voce corrispondente nella raccolta "ICorDebugTypeEnum" sarà un tipo `ELEMENT_TYPE_END` per gli errori a causa di problemi di recupero dei dati, o `ELEMENT_TYPE_VOID` per interfaccia sconosciuto identificatori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
