---
title: Metodo ICorDebugManagedCallback2::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: f40030a2034057e83de51a21655a686f30b9ee88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137448"
---
# <a name="icordebugmanagedcallback2exception-method"></a>Metodo ICorDebugManagedCallback2::Exception
Notifica al debugger che è stata avviata una ricerca di un gestore di eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread in cui è stata generata l'eccezione.  
  
 `pThread`  
 in Puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.  
  
 `pFrame`  
 in Puntatore a un oggetto ICorDebugFrame che rappresenta un frame, come determinato dal parametro `dwEventType`. Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.  
  
 `nOffset`  
 in Intero che specifica un offset, come determinato dal parametro `dwEventType`. Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.  
  
 `dwEventType`  
 in Valore dell'enumerazione CorDebugExceptionCallbackType che specifica il tipo di questo callback di eccezione.  
  
 `dwFlags`  
 in Valore dell'enumerazione [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) che specifica informazioni aggiuntive sull'eccezione  
  
## <a name="remarks"></a>Note  
 Il callback `Exception` viene chiamato in diversi punti durante la fase di ricerca del processo di gestione delle eccezioni. Ovvero, può essere chiamato più volte durante la rimozione di un'eccezione.  
  
 L'eccezione elaborata può essere recuperata dall'oggetto ICorDebugThread a cui fa riferimento il parametro `pThread`.  
  
 Il frame e l'offset specifici sono determinati dal parametro `dwEventType` come indicato di seguito:  
  
|Valore di `dwEventType`|Valore di `pFrame`|Valore di `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Frame che ha generato l'eccezione.|Puntatore all'istruzione nel frame.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Frame del codice utente più vicino al punto dell'eccezione generata.|Puntatore all'istruzione nel frame.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Frame che contiene il gestore catch.|Offset MSIL (Microsoft Intermediate Language) dell'inizio del gestore catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Non definito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
