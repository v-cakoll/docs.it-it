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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faefff879142d66c4c596f1b30a25e349a4014b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2exception-method"></a>Metodo ICorDebugManagedCallback2::Exception
Notifica al debugger che si è iniziata una ricerca di un gestore di eccezioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread su cui è stata generata l'eccezione.  
  
 `pThread`  
 [in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread su cui è stata generata l'eccezione.  
  
 `pFrame`  
 [in] Un puntatore a un oggetto ICorDebugFrame che rappresenta un frame, come determinato dal `dwEventType` parametro. Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.  
  
 `nOffset`  
 [in] Valore intero che specifica un offset, come determinato dal `dwEventType` parametro. Per ulteriori informazioni, vedere la tabella nella sezione Osservazioni.  
  
 `dwEventType`  
 [in] Valore dell'enumerazione CorDebugExceptionCallbackType che specifica il tipo di callback dell'eccezione.  
  
 `dwFlags`  
 [in] Il valore di [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumerazione che specifica informazioni aggiuntive sull'eccezione  
  
## <a name="remarks"></a>Note  
 Il `Exception` callback viene chiamato in vari momenti durante la fase di ricerca del processo di gestione delle eccezioni. Ovvero, può essere chiamato più volte durante la rimozione di un'eccezione.  
  
 L'eccezione in fase di elaborazione può essere recuperato dall'oggetto ICorDebugThread a cui fa riferimento il `pThread` parametro.  
  
 Il frame e l'offset sono determinati dalle `dwEventType` parametro come indicato di seguito:  
  
|Valore di `dwEventType`|Valore di `pFrame`|Valore di `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Frame che ha generato l'eccezione.|Puntatore all'istruzione nel frame.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Il frame di codice utente più vicino al punto dell'eccezione generata.|Puntatore all'istruzione nel frame.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Il frame che contiene il gestore catch.|Offset Microsoft intermediate language (MSIL) dell'inizio del gestore catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Non è definito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
