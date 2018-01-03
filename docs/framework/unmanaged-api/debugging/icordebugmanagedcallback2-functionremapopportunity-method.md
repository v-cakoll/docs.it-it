---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 208803acea65b24429938dc646e7abe70949b237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
Notifica al debugger che l'esecuzione del codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente la funzione modificata.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread su cui è stato rilevato il punto di interruzione di modifica del mapping.  
  
 `pOldFunction`  
 [in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione sul thread.  
  
 `pNewFunction`  
 [in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.  
  
 `oldILOffset`  
 [in] Offset Microsoft intermediate language (MSIL) del puntatore all'istruzione nella versione precedente della funzione.  
  
## <a name="remarks"></a>Note  
 Questo callback consente al debugger la possibilità di modificare il mapping al puntatore all'istruzione al suo posto nella nuova versione della funzione specificata mediante la chiamata di [ICorDebugILFrame2:: RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) metodo. Se il debugger non chiama `RemapFunction` prima di chiamare il [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) (metodo), il runtime continuerà a eseguire il codice obsoleto e verrà generato un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.  
  
 Verrà richiamato il callback di ogni frame è in esecuzione una versione precedente della funzione specificata fino a quando il debugger restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
