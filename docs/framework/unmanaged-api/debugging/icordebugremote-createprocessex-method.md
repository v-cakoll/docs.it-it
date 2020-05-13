---
title: Metodo ICorDebugRemote::CreateProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
ms.openlocfilehash: 4b2689f04228c9ecbbbb18531a0aefd3c40e3072
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377988"
---
# <a name="icordebugremotecreateprocessex-method"></a>Metodo ICorDebugRemote::CreateProcessEx
Avvia un processo in un computer remoto nel debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRemoteTarget`  
 in Puntatore a un' [interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Utilizzato per determinare il computer remoto in cui verrà avviato il processo.  
  
 `lpApplicationName`  
 in Puntatore a una stringa con terminazione null che specifica il modulo che deve essere eseguito dal processo avviato. Il modulo viene eseguito nel contesto di sicurezza del processo chiamante.  
  
 `lpCommandLine`  
 in Puntatore a una stringa con terminazione null che specifica la riga di comando che deve essere eseguita dal processo avviato.  
  
 `lpProcessAttributes`  
 in Non usato per il debug remoto.  
  
 `lpThreadAttributes`  
 in Non usato per il debug remoto.  
  
 `bInheritHandles`  
 in Non usato per il debug remoto.  
  
 `dwCreationFlags`  
 in Non usato per il debug remoto.  
  
 `lpEnvironment`  
 in Puntatore a un blocco di ambiente per il nuovo processo.  
  
 `lpCurrentDirectory`  
 in Puntatore a una stringa con terminazione null che specifica il percorso completo della directory corrente per il processo. Se questo parametro è null, il nuovo processo avrà la stessa unità e la stessa directory correnti del processo chiamante.  
  
 `lpStartupInfo`  
 in Non usato per il debug remoto.  
  
 `lpProcessInformation`  
 in Non usato per il debug remoto.  
  
 `debuggingFlags`  
 in Non usato per il debug remoto.  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugProcess Interface" che rappresenta il processo.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il processo è stato avviato nel computer remoto ed è stata restituita un'interfaccia "ICorDebugProcess" per il debug.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Non è possibile avviare il processo nel computer remoto e restituire un'interfaccia "ICorDebugProcess" per il debug.  
  
## <a name="remarks"></a>Osservazioni  
 Il debug in modalità mista non è supportato in Silverlight.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemote](icordebugremote-interface.md)
- [Interfaccia ICorDebug](icordebug-interface.md)

- [Interfacce di debug](debugging-interfaces.md)
