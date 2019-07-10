---
title: Metodo ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83bb52f7f2035605914e2fe72ce2daf78de5bc1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749911"
---
# <a name="icordebugcontrollerstop-method"></a>Metodo ICorDebugController::Stop
Esegue un arresto cooperativo in tutti i thread che eseguono il codice gestito nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwTimeoutIgnored`  
 Non usato.  
  
## <a name="remarks"></a>Note  
 `Stop` esegue un'interruzione cooperativa in tutti i thread che esegue codice gestito nel processo. Durante una sessione di debug solo gestito, i thread non gestiti possono continuare a eseguire (ma verrà bloccata durante il tentativo di chiamare codice gestito). Durante una sessione di debug di interoperabilità, i thread non gestiti verranno arrestati. Il `dwTimeoutIgnored` valore viene attualmente ignorato e trattato come INFINITE (-1). Se l'arresto cooperativo ha esito negativo a causa di un deadlock, tutti i thread vengono sospesi ed E_TIMEOUT viene restituito.  
  
> [!NOTE]
>  `Stop` è l'unico metodo sincrono nell'API di debug. Quando si `Stop` restituisce S_OK, il processo è stato arrestato. Non viene assegnato alcun callback per notificare ai listener dell'interruzione. Il debugger deve chiamare [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per consentire la ripresa del processo.  
  
 Il debugger mantiene un contatore di arresto. Quando il conteggio arrivasse a zero, viene ripreso il controller. Ogni chiamata a `Stop` o ogni callback inviato viene incrementato il contatore. Ogni chiamata a `ICorDebugController::Continue` decrementa il contatore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
