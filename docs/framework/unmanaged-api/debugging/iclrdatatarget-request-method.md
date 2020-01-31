---
title: Metodo ICLRDataTarget::Request
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 0a7e764d89dd42bcaf81da5cf6a16991b6b8a16e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793698"
---
# <a name="iclrdatatargetrequest-method"></a>Metodo ICLRDataTarget::Request
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per richiedere un'operazione, come definito dall'implementazione di.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `reqCode`  
 in Definito dall'utente.  
  
 `inBufferSize`  
 in Dimensioni del buffer di input, che viene utilizzato per la richiesta in ingresso.  
  
 `inBuffer`  
 in Buffer contenente la richiesta.  
  
 `outBufferSize`  
 in Dimensione del buffer di output utilizzata per la risposta.  
  
 `outBuffer`  
 out Buffer contenente la risposta.  
  
## <a name="remarks"></a>Note  
 Il metodo `Request` facilita l'aggiunta di operazioni personalizzate non specificate. Questo metodo fornisce l'estendibilità senza richiedere la revisione della definizione dell'interfaccia.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget](iclrdatatarget-interface.md)
