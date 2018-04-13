---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a7ce44dcfc709b4fea1952471cf31f5f07d4d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Ottiene un enumeratore per memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] basato su tipi in un dominio applicazione in base ai relativi identificatori di interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cReqTypes`  
 [in] Il numero di tipi richiesti.  
  
 `iidsToResolve`  
 [in] Un puntatore a una matrice che contiene gli identificatori di interfaccia corrispondenti per le rappresentazioni di gestito il [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi da recuperare.  
  
 `ppTypesEnum`  
 [out] Puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugTypeEnum" che consente l'enumerazione di memorizzato nella cache gestite le rappresentazioni del [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi recuperato, in base agli identificatori di interfaccia in `iidsToResolve`.  
  
## <a name="remarks"></a>Note  
 Se il metodo non riesce a recuperare le informazioni per un identificatore di interfaccia specifica, la voce corrispondente nella raccolta "ICorDebugTypeEnum" verrà assegnato un tipo di `ELEMENT_TYPE_END` per gli errori a causa di problemi di recupero dei dati, o `ELEMENT_TYPE_VOID` per interfaccia sconosciuta identificatori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
