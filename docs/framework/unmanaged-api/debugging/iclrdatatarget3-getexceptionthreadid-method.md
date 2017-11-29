---
title: Metodo ICLRDataTarget3::GetExceptionThreadID
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionThreadID
api_location: mscordbi.dll
api_type: COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f05d264d4bf55de930a07eda6bf369570c8b7fa8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>Metodo ICLRDataTarget3::GetExceptionThreadID
Chiamato dai servizi di accesso ai dati CLR (Common Language Runtime) per ottenere l'ID del thread che ha generato l'eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `threadID`  
 [out] ID del thread che ha generato l'eccezione.  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo. I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|`S_OK`|Il metodo è riuscito.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Non è possibile trovare un ID di thread valido per l'eccezione.|  
  
## <a name="remarks"></a>Note  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, Clrdata. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [Metodo GetExceptionContextRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [Metodo GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
