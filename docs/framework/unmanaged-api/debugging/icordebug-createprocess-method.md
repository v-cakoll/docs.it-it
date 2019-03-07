---
title: Metodo ICorDebug::CreateProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf7480eaa0fa38651d139a2fa9d533b43dbdce1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496469"
---
# <a name="icordebugcreateprocess-method"></a>Metodo ICorDebug::CreateProcess
Avvia un processo e il thread principale sotto il controllo del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lpApplicationName`  
 [in] Puntatore a una stringa con terminazione null che specifica il modulo deve essere eseguito dal processo avviato. Il modulo viene eseguito nel contesto di sicurezza del processo chiamante.  
  
 `lpCommandLine`  
 [in] Puntatore a una stringa con terminazione null che specifica la riga di comando deve essere eseguito dal processo avviato. Il nome dell'applicazione (ad esempio, "SomeApp.exe") deve essere il primo argomento.  
  
 `lpProcessAttributes`  
 [in] Puntatore a un Win32 `SECURITY_ATTRIBUTES` struttura che specifica il descrittore di sicurezza per il processo. Se `lpProcessAttributes` è null, il processo Ottiene un descrittore di sicurezza predefinito.  
  
 `lpThreadAttributes`  
 [in] Puntatore a un Win32 `SECURITY_ATTRIBUTES` struttura che specifica il descrittore di sicurezza per il thread principale del processo. Se `lpThreadAttributes` è null, il thread Ottiene un descrittore di sicurezza predefinito.  
  
 `bInheritHandles`  
 [in] Impostare su `true` per indicare che ogni handle ereditabile nel processo chiamante viene ereditato dal processo avviato, o `false` per indicare che l'handle non vengono ereditati. I punti di controllo ereditati sono gli stessi diritti di accesso e valore come gli handle originali.  
  
 `dwCreationFlags`  
 [in] Una combinazione bit per bit del [flag di creazione processo Win32](https://go.microsoft.com/fwlink/?linkid=69981) che controllano la classe di priorità e il comportamento del processo avviato.  
  
 `lpEnvironment`  
 [in] Puntatore a un blocco di ambiente per il nuovo processo.  
  
 `lpCurrentDirectory`  
 [in] Puntatore a una stringa con terminazione null che specifica il percorso completo per directory corrente per il processo. Se questo parametro è null, il nuovo processo avrà la stessa unità e directory corrente del processo chiamante.  
  
 `lpStartupInfo`  
 [in] Puntatore a un Win32 `STARTUPINFOW` struttura che specifica la postazione, desktop, gli handle di standard e aspetto della finestra principale per il processo avviato.  
  
 `lpProcessInformation`  
 [in] Puntatore a un Win32 `PROCESS_INFORMATION` struttura che specifica le informazioni di identificazione sul processo da avviare.  
  
 `debuggingFlags`  
 [in] Valore dell'enumerazione CorDebugCreateProcessFlags che specifica le opzioni di debug.  
  
 `ppProcess`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 I parametri di questo metodo sono identici a quelli di Win32 `CreateProcess` (metodo).  
  
 Per abilitare il debug in modalità mista non gestiti, impostare `dwCreationFlags` su DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS. Se si desidera usare solo il debug gestito, non impostare questi flag.  
  
 Se il debugger e il processo per essere eseguito il debug (il processo associato) condividere un'unica console e se il debug di interoperabilità viene usato, è possibile che il processo associato a mantenere attivi i blocchi console e terminare con un evento di debug. Il debugger verrà quindi bloccare qualsiasi tentativo di utilizzare la console. Per evitare questo problema, impostare il flag CREATE_NEW_CONSOLE `dwCreationFlags` parametro.  
  
 Debug di interoperabilità non è supportato nelle piattaforme Win9x e non x86, ad esempio le piattaforme basate su IA-64 e AMD64 basato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
