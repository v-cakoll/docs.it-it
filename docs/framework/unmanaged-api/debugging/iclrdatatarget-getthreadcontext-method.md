---
title: Metodo ICLRDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1492c6d72d68a95a79925d7789a710b5b5ed14b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738700"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Metodo ICLRDataTarget::GetThreadContext
Ottiene il contesto di esecuzione corrente per il thread nel processo di destinazione specificato. Questo metodo viene chiamato dai servizi di accesso dati di common language runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 [in] L'identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `contextFlags`  
 [in] Flag che specificano le parti del contesto da restituire. L'implementazione restituisce almeno le parti del contesto.  
  
 `contextSize`  
 [in] Le dimensioni del contesto.  
  
 `context`  
 [out] Puntatore a un buffer in cui inserire il contesto.  
  
 I dati di `context` buffer deve essere nel formato Win32 `CONTEXT` struttura. Il contesto specifica i dati di registro specifico del processore, pertanto la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore. Fare riferimento al file di intestazione Winnt. H per la definizione di Win32 `CONTEXT` struttura.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, ClrData.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
