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
ms.openlocfilehash: 8b259636a8bd28abd3bba12c4a05dda3c13557e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784897"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Metodo ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Ottiene un enumeratore per i tipi di Windows Runtime memorizzati nella cache in un dominio applicazione in base ai relativi identificatori di interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cReqTypes`  
 in Numero di tipi necessari.  
  
 `iidsToResolve`  
 in Puntatore a una matrice contenente gli identificatori di interfaccia corrispondenti alle rappresentazioni gestite dei tipi di Windows Runtime da recuperare.  
  
 `ppTypesEnum`  
 out Puntatore all'indirizzo di un oggetto interfaccia "ICorDebugTypeEnum" che consente l'enumerazione delle rappresentazioni gestite memorizzate nella cache dei tipi di Windows Runtime recuperati, in base agli identificatori di interfaccia in `iidsToResolve`.  
  
## <a name="remarks"></a>Note  
 Se il metodo non riesce a recuperare informazioni per un identificatore di interfaccia specifico, la voce corrispondente nella raccolta "ICorDebugTypeEnum" avrà un tipo di `ELEMENT_TYPE_END` per gli errori causati da problemi di recupero dei dati o `ELEMENT_TYPE_VOID` per gli identificatori di interfaccia sconosciuti.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** Windows Runtime  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAppDomain3](icordebugappdomain3-interface.md)
