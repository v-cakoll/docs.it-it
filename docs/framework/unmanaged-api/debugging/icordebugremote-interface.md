---
title: Interfaccia ICorDebugRemote
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemote
helpviewer_keywords: ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6195b53d11877c6b7b2a52c3fd8d194dfb51810
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremote-interface"></a>Interfaccia ICorDebugRemote
Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo icordebugremote:: Createprocessex](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|Crea un processo in un computer remoto per il debug gestito.|  
|[Metodo icordebugremote:: Debugactiveprocessex](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|Avvia un processo in un computer remoto all'interno del debugger.|  
  
## <a name="remarks"></a>Note  
 Attualmente, questa funzionalità è supportata solo per il debug di applicazioni basate su Silverlight di destinazione in cui è in esecuzione in un computer Macintosh remoto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugRemoteTarget (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
