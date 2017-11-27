---
title: Metodo ICorDebugAppDomain3::GetCachedWinRTTypes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3.GetCachedWinRTTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb41b278b21b2289c7f5a7164a1bd01bc39423b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>Metodo ICorDebugAppDomain3::GetCachedWinRTTypes
Ottiene un enumeratore per tutti memorizzati nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppGuidToTypeEnum`  
 [out] Un puntatore a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) oggetto dell'interfaccia che può enumerare le rappresentazioni di gestito [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipi attualmente caricati nel dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugAppDomain3 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
