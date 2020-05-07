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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860602"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>Metodo ICLRDataTarget::GetThreadContext
Ottiene il contesto di esecuzione corrente per il thread specificato nel processo di destinazione. Questo metodo viene chiamato dal servizio di accesso ai dati Common Language Runtime.  
  
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
 in Identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `contextFlags`  
 in Flag che specificano le parti del contesto da restituire. L'implementazione restituirà almeno queste parti del contesto.  
  
 `contextSize`  
 in Dimensioni del contesto.  
  
 `context`  
 out Puntatore a un buffer in cui inserire il contesto.  
  
 I dati nel `context` buffer devono essere nel formato della struttura Win32 `CONTEXT` . Il contesto specifica i dati del registro specifici del processore, pertanto la definizione della `CONTEXT` struttura Win32 dipende dall'architettura del processore. Per la definizione della struttura Win32 `CONTEXT` , fare riferimento al file di intestazione Winnt. h.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)
