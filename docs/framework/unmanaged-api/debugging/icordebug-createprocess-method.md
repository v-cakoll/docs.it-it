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
ms.openlocfilehash: cb16bae2dfe151d04c40269a8e6872ecb49b4269
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789002"
---
# <a name="icordebugcreateprocess-method"></a>Metodo ICorDebug::CreateProcess
Avvia un processo e il relativo thread primario sotto il controllo del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Puntatore a una stringa con terminazione null che specifica il modulo che deve essere eseguito dal processo avviato. Il modulo viene eseguito nel contesto di sicurezza del processo chiamante.  
  
 `lpCommandLine`  
 in Puntatore a una stringa con terminazione null che specifica la riga di comando che deve essere eseguita dal processo avviato. Il nome dell'applicazione (ad esempio, "SomeApp. exe") deve essere il primo argomento.  
  
 `lpProcessAttributes`  
 in Puntatore a una struttura di `SECURITY_ATTRIBUTES` Win32 che specifica il descrittore di sicurezza per il processo. Se `lpProcessAttributes` è null, il processo ottiene un descrittore di sicurezza predefinito.  
  
 `lpThreadAttributes`  
 in Puntatore a una struttura di `SECURITY_ATTRIBUTES` Win32 che specifica il descrittore di sicurezza per il thread principale del processo. Se `lpThreadAttributes` è null, il thread ottiene un descrittore di sicurezza predefinito.  
  
 `bInheritHandles`  
 in Impostare su `true` per indicare che ogni handle ereditabile nel processo chiamante viene ereditato dal processo avviato oppure `false` per indicare che gli handle non vengono ereditati. Gli handle ereditati hanno lo stesso valore e i diritti di accesso degli handle originali.  
  
 `dwCreationFlags`  
 in Combinazione bit per bit dei [flag di creazione del processo Win32](/windows/win32/procthread/process-creation-flags) che controllano la classe di priorità e il comportamento del processo avviato.  
  
 `lpEnvironment`  
 in Puntatore a un blocco di ambiente per il nuovo processo.  
  
 `lpCurrentDirectory`  
 in Puntatore a una stringa con terminazione null che specifica il percorso completo della directory corrente per il processo. Se questo parametro è null, il nuovo processo avrà la stessa unità e la stessa directory correnti del processo chiamante.  
  
 `lpStartupInfo`  
 in Puntatore a una struttura di `STARTUPINFOW` Win32 che specifica la stazione della finestra, il desktop, gli handle standard e l'aspetto della finestra principale per il processo avviato.  
  
 `lpProcessInformation`  
 in Puntatore a una struttura di `PROCESS_INFORMATION` Win32 che specifica le informazioni di identificazione relative al processo da avviare.  
  
 `debuggingFlags`  
 in Valore dell'enumerazione CorDebugCreateProcessFlags che specifica le opzioni di debug.  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.  
  
## <a name="remarks"></a>Note  
 I parametri di questo metodo sono identici a quelli del metodo Win32 `CreateProcess`.  
  
 Per abilitare il debug in modalità mista non gestita, impostare `dwCreationFlags` su &#124; DEBUG_PROCESS DEBUG_ONLY_THIS_PROCESS. Se si desidera utilizzare solo il debug gestito, non impostare questi flag.  
  
 Se il debugger e il processo di cui è in corso il debug (il processo collegato) condividono un'unica console e se viene usato il debug di interoperabilità, è possibile che il processo collegato mantenga i blocchi della console e arresti in corrispondenza di un evento di debug. Il debugger bloccherà quindi qualsiasi tentativo di usare la console. Per evitare questo problema, impostare il flag CREATE_NEW_CONSOLE nel parametro `dwCreationFlags`.  
  
 Il debug di interoperabilità non è supportato in piattaforme Win9x e non x86, ad esempio piattaforme basate su IA-64 e AMD64.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
