---
title: Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14291ced9a606cc0b2a3792c2157b7bc2a3460a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190535"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>Metodo ICorDebugManagedCallback2::FunctionRemapOpportunity
Notifica al debugger che l'esecuzione di codice ha raggiunto un punto di sequenza in una versione precedente di una funzione modificata.  
  
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
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la funzione modificata.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato rilevato il punto di interruzione di modifica del mapping.  
  
 `pOldFunction`  
 [in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione della funzione attualmente in esecuzione sul thread.  
  
 `pNewFunction`  
 [in] Un puntatore a un oggetto ICorDebugFunction che rappresenta la versione più recente della funzione.  
  
 `oldILOffset`  
 [in] Offset Microsoft intermediate language (MSIL) del puntatore dell'istruzione nella versione precedente della funzione.  
  
## <a name="remarks"></a>Note  
 Questo callback consente al debugger di un'opportunità per rimappare il puntatore all'istruzione al suo posto nella nuova versione della funzione specificata mediante la chiamata di [ICorDebugILFrame2::RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) (metodo). Se non ne richiama il debugger `RemapFunction` prima di chiamare il [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metodo, il runtime continua a eseguire il codice precedente e verrà generato un altro `FunctionRemapOpportunity` callback al successivo punto di sequenza.  
  
 Questo callback verrà richiamato per ogni fotogramma che è in esecuzione una versione precedente della funzione specificata fino a quando il debugger restituisce S_OK.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
