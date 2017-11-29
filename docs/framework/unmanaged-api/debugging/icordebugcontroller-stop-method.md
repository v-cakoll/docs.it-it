---
title: Metodo ICorDebugController::Stop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Stop
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b92d07f8d162123d20c6861d204d73789060906
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerstop-method"></a>Metodo ICorDebugController::Stop
Esegue un'interruzione cooperativa su tutti i thread che eseguono codice gestito nel processo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwTimeoutIgnored`  
 Non usato.  
  
## <a name="remarks"></a>Note  
 `Stop`esegue un'interruzione cooperativa su tutti i thread che esegue codice gestito nel processo. Durante una sessione di debug solo gestito, il thread non gestito è possibile continuare l'esecuzione (ma verrà bloccata durante il tentativo di chiamare codice gestito). Durante una sessione di debug di interoperabilità, il thread non gestito verrà arrestato. Il `dwTimeoutIgnored` valore attualmente viene ignorato e trattato come infinito (-1). Se l'interruzione cooperativa ha esito negativo a causa di un deadlock, tutti i thread vengono sospesi e verrà restituito E_TIMEOUT.  
  
> [!NOTE]
>  `Stop`è l'unico metodo sincrono nell'API di debug. Quando `Stop` restituisce S_OK, il processo è stato arrestato. Il callback non viene assegnato da notificare listener dell'interruzione. Il debugger deve chiamare [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per consentire la ripresa del processo.  
  
 Il debugger gestisce un contatore di arresto. Quando il contatore è pari a zero, il controller viene ripreso. Ogni chiamata a `Stop` o ogni callback inviato incrementa il contatore. Ogni chiamata a `ICorDebugController::Continue` decrementa il contatore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 
