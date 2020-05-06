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
ms.openlocfilehash: b9ae2b36bff9b4a6c048a8de99fa7d09350b1401
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859715"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="74122-102">Metodo ICorDebug::CreateProcess</span><span class="sxs-lookup"><span data-stu-id="74122-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="74122-103">Avvia un processo e il relativo thread primario sotto il controllo del debugger.</span><span class="sxs-lookup"><span data-stu-id="74122-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74122-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74122-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="74122-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74122-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="74122-106">in Puntatore a una stringa con terminazione null che specifica il modulo che deve essere eseguito dal processo avviato.</span><span class="sxs-lookup"><span data-stu-id="74122-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="74122-107">Il modulo viene eseguito nel contesto di sicurezza del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="74122-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="74122-108">in Puntatore a una stringa con terminazione null che specifica la riga di comando che deve essere eseguita dal processo avviato.</span><span class="sxs-lookup"><span data-stu-id="74122-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="74122-109">Il nome dell'applicazione (ad esempio, "SomeApp. exe") deve essere il primo argomento.</span><span class="sxs-lookup"><span data-stu-id="74122-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="74122-110">in Puntatore a una struttura `SECURITY_ATTRIBUTES` Win32 che specifica il descrittore di sicurezza per il processo.</span><span class="sxs-lookup"><span data-stu-id="74122-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="74122-111">Se `lpProcessAttributes` è null, il processo ottiene un descrittore di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="74122-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="74122-112">in Puntatore a una struttura `SECURITY_ATTRIBUTES` Win32 che specifica il descrittore di sicurezza per il thread principale del processo.</span><span class="sxs-lookup"><span data-stu-id="74122-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="74122-113">Se `lpThreadAttributes` è null, il thread ottiene un descrittore di sicurezza predefinito.</span><span class="sxs-lookup"><span data-stu-id="74122-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="74122-114">in Impostare su `true` per indicare che ogni handle ereditabile nel processo chiamante viene ereditato dal processo avviato o `false` per indicare che gli handle non vengono ereditati.</span><span class="sxs-lookup"><span data-stu-id="74122-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="74122-115">Gli handle ereditati hanno lo stesso valore e i diritti di accesso degli handle originali.</span><span class="sxs-lookup"><span data-stu-id="74122-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="74122-116">in Combinazione bit per bit dei [flag di creazione del processo Win32](/windows/win32/procthread/process-creation-flags) che controllano la classe di priorità e il comportamento del processo avviato.</span><span class="sxs-lookup"><span data-stu-id="74122-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="74122-117">in Puntatore a un blocco di ambiente per il nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="74122-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="74122-118">in Puntatore a una stringa con terminazione null che specifica il percorso completo della directory corrente per il processo.</span><span class="sxs-lookup"><span data-stu-id="74122-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="74122-119">Se questo parametro è null, il nuovo processo avrà la stessa unità e la stessa directory correnti del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="74122-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="74122-120">in Puntatore a una struttura `STARTUPINFOW` Win32 che specifica la stazione della finestra, il desktop, gli handle standard e l'aspetto della finestra principale per il processo avviato.</span><span class="sxs-lookup"><span data-stu-id="74122-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="74122-121">in Puntatore a una struttura `PROCESS_INFORMATION` Win32 che specifica le informazioni di identificazione relative al processo da avviare.</span><span class="sxs-lookup"><span data-stu-id="74122-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="74122-122">in Valore dell'enumerazione CorDebugCreateProcessFlags che specifica le opzioni di debug.</span><span class="sxs-lookup"><span data-stu-id="74122-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="74122-123">out Puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="74122-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74122-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="74122-124">Remarks</span></span>  
 <span data-ttu-id="74122-125">I parametri di questo metodo sono gli stessi di quelli del metodo Win32 `CreateProcess` .</span><span class="sxs-lookup"><span data-stu-id="74122-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="74122-126">Per abilitare il debug in modalità mista non gestita, `dwCreationFlags` impostare su DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span><span class="sxs-lookup"><span data-stu-id="74122-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="74122-127">Se si desidera utilizzare solo il debug gestito, non impostare questi flag.</span><span class="sxs-lookup"><span data-stu-id="74122-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="74122-128">Se il debugger e il processo di cui è in corso il debug (il processo collegato) condividono un'unica console e se viene usato il debug di interoperabilità, è possibile che il processo collegato mantenga i blocchi della console e arresti in corrispondenza di un evento di debug.</span><span class="sxs-lookup"><span data-stu-id="74122-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="74122-129">Il debugger bloccherà quindi qualsiasi tentativo di usare la console.</span><span class="sxs-lookup"><span data-stu-id="74122-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="74122-130">Per evitare questo problema, impostare il flag CREATE_NEW_CONSOLE nel `dwCreationFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="74122-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="74122-131">Il debug di interoperabilità non è supportato in piattaforme Win9x e non x86, ad esempio piattaforme basate su IA-64 e AMD64.</span><span class="sxs-lookup"><span data-stu-id="74122-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74122-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74122-132">Requirements</span></span>  
 <span data-ttu-id="74122-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74122-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74122-134">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74122-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74122-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74122-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74122-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74122-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74122-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74122-137">See also</span></span>

- [<span data-ttu-id="74122-138">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="74122-138">ICorDebug Interface</span></span>](icordebug-interface.md)
