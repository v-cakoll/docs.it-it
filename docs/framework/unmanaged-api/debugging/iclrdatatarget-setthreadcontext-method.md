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
ms.openlocfilehash: cdf5776e1ac9907e63aba0e0d400e48aff683d51
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785291"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>Metodo ICLRDataTarget::SetThreadContext
Imposta il contesto corrente del thread specificato nel processo di destinazione. Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 in Identificatore del sistema operativo di un thread nel processo di destinazione.  
  
 `contextSize`  
 in Dimensioni del contesto.  
  
 `context`  
 in Puntatore a un buffer contenente il contesto.  
  
 I dati nel buffer di `context` saranno nel formato della struttura di `CONTEXT` Win32. Il contesto specifica i dati del registro specifici del processore, pertanto la definizione della struttura Win32 `CONTEXT` dipende dall'architettura del processore. Fare riferimento al file di intestazione WinNT. h per la definizione della struttura `CONTEXT` di Win32.  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)
