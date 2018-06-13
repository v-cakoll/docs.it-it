---
title: Metodo ICLRDataTarget3::GetExceptionContextRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b07318406268023e2d66259b2cb68750d64613e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408164"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Metodo ICLRDataTarget3::GetExceptionContextRecord
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di contesto associato al processo destinazione. Ad esempio, per una destinazione del dump, sarebbe equivalente al record di contesto passato tramite la `ExceptionParam` argomento per il [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) funzione nella libreria di Windows eseguire il Debug della Guida (DbgHelp).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bufferSize`  
 [in] La dimensione del buffer di input, in byte. Questa deve essere sufficientemente grande per poter contenere il record di contesto.  
  
 `bufferUsed`  
 [out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.  
  
 `buffer`  
 [out] Un puntatore a un buffer di memoria che riceve una copia del record di contesto. Il record di eccezione viene restituito come un [contesto](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) tipo.  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo. I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|`S_OK`|Il metodo è riuscito. Il record di contesto è stato copiato nel buffer di output.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Nessun record di contesto è associato alla destinazione.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|La dimensione del buffer di input non è sufficientemente grande per poter contenere il record di contesto.|  
  
## <a name="remarks"></a>Note  
 [CONTESTO](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) è una struttura specifica della piattaforma definita nelle intestazioni fornite da Windows SDK.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Clrdata. idl, Clrdata. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [Metodo GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [Metodo GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
