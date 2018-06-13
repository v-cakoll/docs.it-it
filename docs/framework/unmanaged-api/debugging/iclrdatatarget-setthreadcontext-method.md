---
title: Metodo ICLRDataTarget::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73697fdd19f2492aabdc0d76e8c1a27c917c85f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405538"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>Metodo ICLRDataTarget::SetThreadContext
Imposta il contesto corrente del thread specificato nel processo di destinazione. Questo metodo viene chiamato da servizi di accesso dati di common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [in] Identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `contextSize`  
 [in] Le dimensioni del contesto.  
  
 `context`  
 [in] Puntatore a un buffer contenente il contesto.  
  
 I dati di `context` buffer sarà nel formato Win32 `CONTEXT` struttura. Il contesto specifica i dati di registro specifici, la definizione di Win32 `CONTEXT` struttura dipende dall'architettura del processore. Fare riferimento al file di intestazione Winnt. H per la definizione dell'oggetto Win32 `CONTEXT` struttura.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
