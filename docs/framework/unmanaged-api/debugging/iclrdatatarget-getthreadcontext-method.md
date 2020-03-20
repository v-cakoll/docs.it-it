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
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179172"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Metodo ICLRDataTarget::GetThreadContext
Ottiene il contesto di esecuzione corrente per il thread specificato nel processo di destinazione. Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime.  
  
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
 [in] Identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `contextFlags`  
 [in] Flag che specificano le parti del contesto da restituire. L'implementazione restituirà almeno queste parti del contesto.  
  
 `contextSize`  
 [in] Dimensione del contesto.  
  
 `context`  
 [fuori] Puntatore a un buffer in cui inserire il contesto.  
  
 I dati `context` nel buffer devono essere nel formato `CONTEXT` della struttura Win32. Il contesto specifica i dati del registro specifici `CONTEXT` del processore, pertanto la definizione della struttura Win32 dipende dall'architettura del processore. Fare riferimento al file di intestazione WinNT.h `CONTEXT` per la definizione della struttura Win32.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, ClrData.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)
