---
title: Metodo ICorDebug::CreateProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="81a0e-102">Metodo ICorDebug::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="81a0e-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="81a0e-103">Avvia un processo e il relativo thread primario sotto il controllo del debugger.</span><span class="sxs-lookup"><span data-stu-id="81a0e-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81a0e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81a0e-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="81a0e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81a0e-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="81a0e-106">[in] Puntatore a una stringa con terminazione null che specifica il modulo deve essere eseguito dal processo avviato.</span><span class="sxs-lookup"><span data-stu-id="81a0e-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="81a0e-107">Il modulo viene eseguito nel contesto di sicurezza del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="81a0e-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="81a0e-108">[in] Puntatore a una stringa con terminazione null che specifica la riga di comando da eseguire tramite il processo avviato.</span><span class="sxs-lookup"><span data-stu-id="81a0e-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="81a0e-109">Il nome dell'applicazione (ad esempio, "SomeApp.exe") deve essere il primo argomento.</span><span class="sxs-lookup"><span data-stu-id="81a0e-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="81a0e-110">[in] Puntatore a un Win32 `SECURITY_ATTRIBUTES` struttura che specifica il descrittore di sicurezza per il processo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="81a0e-111">Se `lpProcessAttributes` è null, il processo Ottiene un descrittore di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="81a0e-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="81a0e-112">[in] Puntatore a un Win32 `SECURITY_ATTRIBUTES` struttura che specifica il descrittore di sicurezza per il thread principale del processo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="81a0e-113">Se `lpThreadAttributes` è null, il thread Ottiene un descrittore di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="81a0e-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="81a0e-114">[in] Impostare su `true` per indicare che ogni handle ereditabile nel processo chiamante viene ereditato dal processo avviato, o `false` per indicare che l'handle non vengono ereditati.</span><span class="sxs-lookup"><span data-stu-id="81a0e-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="81a0e-115">Gli handle ereditati hanno gli stessi diritti di accesso e valore di handle originali.</span><span class="sxs-lookup"><span data-stu-id="81a0e-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="81a0e-116">[in] Combinazione bit per bit di [flag di creazione processo Win32](http://go.microsoft.com/fwlink/?linkid=69981) che controllano la classe di priorità e il comportamento del processo avviato.</span><span class="sxs-lookup"><span data-stu-id="81a0e-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="81a0e-117">[in] Puntatore a un blocco di ambiente per il nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="81a0e-118">[in] Puntatore a una stringa con terminazione null che specifica il percorso completo della directory corrente per il processo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="81a0e-119">Se questo parametro è null, il nuovo processo avranno la stessa unità e directory corrente del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="81a0e-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="81a0e-120">[in] Puntatore a un Win32 `STARTUPINFOW` struttura che specifica la finestra, desktop, gli handle standard e l'aspetto della finestra principale per il processo avviato.</span><span class="sxs-lookup"><span data-stu-id="81a0e-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="81a0e-121">[in] Puntatore a un Win32 `PROCESS_INFORMATION` struttura che specifica le informazioni di identificazione sul processo da avviare.</span><span class="sxs-lookup"><span data-stu-id="81a0e-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="81a0e-122">[in] Valore dell'enumerazione CorDebugCreateProcessFlags che specifica le opzioni di debug.</span><span class="sxs-lookup"><span data-stu-id="81a0e-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="81a0e-123">[out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81a0e-124">Note</span><span class="sxs-lookup"><span data-stu-id="81a0e-124">Remarks</span></span>  
 <span data-ttu-id="81a0e-125">I parametri di questo metodo sono identici a quelli di Win32 `CreateProcess` metodo.</span><span class="sxs-lookup"><span data-stu-id="81a0e-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="81a0e-126">Per abilitare il debug in modalità mista non gestito, impostare `dwCreationFlags` a DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="81a0e-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="81a0e-127">Se si desidera utilizzare solo il debug gestito, non impostare questi flag.</span><span class="sxs-lookup"><span data-stu-id="81a0e-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="81a0e-128">Se il debugger e il processo di debug (il processo associato) condividono un'unica console, e se il debug di interoperabilità viene usato, è possibile che il processo mantenere attivi i blocchi di console e arrestare in corrispondenza di un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="81a0e-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="81a0e-129">Il debugger verrà quindi bloccare qualsiasi tentativo di utilizzare la console.</span><span class="sxs-lookup"><span data-stu-id="81a0e-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="81a0e-130">Per evitare questo problema, impostare il flag CREATE_NEW_CONSOLE `dwCreationFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="81a0e-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="81a0e-131">Debug di interoperabilità non è supportato sulle piattaforme Win9x e non x86, ad esempio le piattaforme basate su AMD64 e basate su IA-64.</span><span class="sxs-lookup"><span data-stu-id="81a0e-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81a0e-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81a0e-132">Requirements</span></span>  
 <span data-ttu-id="81a0e-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81a0e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81a0e-134">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="81a0e-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81a0e-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81a0e-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81a0e-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81a0e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a0e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81a0e-137">See Also</span></span>  
 [<span data-ttu-id="81a0e-138">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="81a0e-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
