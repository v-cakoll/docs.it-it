---
title: Metodo ICorDebugManagedCallback::StepComplete
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd784cb3322423e9309e8a5632822831b4e44cdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184795"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a>Metodo ICorDebugManagedCallback::StepComplete
Notifica al debugger che è stato completato un passaggio.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stato completato il passaggio.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stato completato il passaggio.  
  
 `pStepper`  
 [in] Un puntatore a un oggetto ICorDebugStepper che rappresenta il passaggio per l'esecuzione di codice.  
  
 `reason`  
 [in] Valore dell'enumerazione CorDebugStepReason che indica il risultato di un singolo passaggio.  
  
## <a name="remarks"></a>Note  
 Il gestore di istruzioni consente di continuare l'esecuzione di istruzioni se si desidera, a meno che il debug viene terminato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
