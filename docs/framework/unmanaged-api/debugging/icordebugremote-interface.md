---
title: Interfaccia ICorDebugRemote
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a50a799c625c647aa275994bc92738b8a4267eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135577"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="3e3ad-102">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="3e3ad-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="3e3ad-103">Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="3e3ad-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e3ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e3ad-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3e3ad-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e3ad-105">Methods</span></span>  
  
|<span data-ttu-id="3e3ad-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3e3ad-106">Method</span></span>|<span data-ttu-id="3e3ad-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e3ad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e3ad-108">Metodo ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="3e3ad-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="3e3ad-109">Crea un processo in un computer remoto per il debug gestito.</span><span class="sxs-lookup"><span data-stu-id="3e3ad-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="3e3ad-110">Metodo ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="3e3ad-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="3e3ad-111">Avvia un processo in un computer remoto all'interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="3e3ad-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e3ad-112">Note</span><span class="sxs-lookup"><span data-stu-id="3e3ad-112">Remarks</span></span>  
 <span data-ttu-id="3e3ad-113">Attualmente, questa funzionalità è supportata solo per il debug di applicazioni basate su Silverlight di destinazione in cui è in esecuzione in un computer Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="3e3ad-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e3ad-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e3ad-114">Requirements</span></span>  
 <span data-ttu-id="3e3ad-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e3ad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e3ad-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e3ad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e3ad-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e3ad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e3ad-118">**Versioni di .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3e3ad-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e3ad-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e3ad-119">See also</span></span>

- [<span data-ttu-id="3e3ad-120">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="3e3ad-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="3e3ad-121">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3e3ad-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="3e3ad-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3e3ad-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
