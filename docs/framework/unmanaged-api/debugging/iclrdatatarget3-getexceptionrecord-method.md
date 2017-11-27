---
title: Metodo ICLRDataTarget3::GetExceptionRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8c9ac4ecc0cffda4038129b1244b81501e9a1f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>Metodo ICLRDataTarget3::GetExceptionRecord
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di eccezione associato al processo destinazione. Ad esempio, per una destinazione del dump, sarebbe equivalente al record di eccezione passato tramite la `ExceptionParam` argomento per il [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) funzione nella libreria di Windows eseguire il Debug della Guida (DbgHelp).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bufferSize`  
 [in] La dimensione del buffer di input, in byte. Deve essere uguale a `sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.  
  
 `bufferUsed`  
 [out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.  
  
 `buffer`  
 [out] Un puntatore a un buffer di memoria che riceve una copia del record di eccezione. Il record di eccezione viene restituito come un [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) tipo.  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo. I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|`S_OK`|Il metodo è riuscito. Il record di eccezione è stato copiato nel buffer di output.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Nessun record di eccezione è associato alla destinazione.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|La dimensione del buffer di input non è uguale a `sizeof(MINIDUMP_EXCEPTION)`.|  
  
## <a name="remarks"></a>Note  
 [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) è una struttura definita in dbghelp. h e Imagehlp in Windows SDK.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, Clrdata. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [Metodo GetExceptionContextRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [Metodo GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
