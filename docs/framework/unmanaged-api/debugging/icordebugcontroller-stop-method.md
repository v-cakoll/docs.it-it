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
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183391"
---
# <a name="icordebugcontrollerstop-method"></a>Metodo ICorDebugController::Stop
Esegue un arresto cooperativo in tutti i thread che eseguono il codice gestito nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
