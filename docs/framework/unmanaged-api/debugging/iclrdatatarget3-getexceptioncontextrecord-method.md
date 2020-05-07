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
ms.openlocfilehash: 3e73d0fc48dcfeafb3fe2f23ec07cdc04a561a9e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860456"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Metodo ICLRDataTarget3::GetExceptionContextRecord
Chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR) per recuperare il record di contesto associato al processo destinazione. Ad esempio, per una destinazione del dump, ciò equivale al record di contesto passato tramite l' `ExceptionParam` argomento alla funzione [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) nella libreria della Guida di debug di Windows (dbghelp).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bufferSize`  
 [in] La dimensione del buffer di input, in byte. Questa deve essere sufficientemente grande per poter contenere il record di contesto.  
  
 `bufferUsed`  
 [out] Un puntatore a un tipo `ULONG32` che riceve il numero di byte effettivamente scritti nel buffer.  
  
 `buffer`  
 [out] Un puntatore a un buffer di memoria che riceve una copia del record di contesto. Il record di eccezione viene restituito come tipo di [contesto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="return-value"></a>Valore restituito  
 Il valore restituito è `S_OK` in caso di esito positivo o un codice di errore `HRESULT` in caso di esito negativo. I codici `HRESULT` possono includere, ma non sono limitati a, quanto segue:  
  
|Codice restituito|Descrizione|  
|-----------------|-----------------|  
|`S_OK`|Il metodo è riuscito. Il record di contesto è stato copiato nel buffer di output.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Nessun record di contesto è associato alla destinazione.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|La dimensione del buffer di input non è sufficientemente grande per poter contenere il record di contesto.|  
  
## <a name="remarks"></a>Osservazioni  
 [Context](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) è una struttura specifica della piattaforma definita nelle intestazioni fornite dal Windows SDK.  
  
 Questo metodo è implementato dal writer dell'applicazione di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataTarget3](iclrdatatarget3-interface.md)
- [Metodo GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)
- [Metodo GetExceptionThreadID](iclrdatatarget3-getexceptionthreadid-method.md)
