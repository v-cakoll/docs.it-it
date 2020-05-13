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
ms.openlocfilehash: ef11aa48f679592126f736c2877c697f02cb5e62
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379238"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="f6a9b-102">Interfaccia ICorDebugRemote</span><span class="sxs-lookup"><span data-stu-id="f6a9b-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="f6a9b-103">Consente di avviare o allegare un debugger gestito a un processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="f6a9b-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6a9b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="f6a9b-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f6a9b-105">Methods</span></span>  
  
|<span data-ttu-id="f6a9b-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f6a9b-106">Method</span></span>|<span data-ttu-id="f6a9b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6a9b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6a9b-108">Metodo ICorDebugRemote::CreateProcessEx</span><span class="sxs-lookup"><span data-stu-id="f6a9b-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="f6a9b-109">Crea un processo in un computer remoto per il debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f6a9b-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="f6a9b-110">Metodo ICorDebugRemote::DebugActiveProcessEx</span><span class="sxs-lookup"><span data-stu-id="f6a9b-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="f6a9b-111">Avvia un processo in un computer remoto nel debugger.</span><span class="sxs-lookup"><span data-stu-id="f6a9b-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6a9b-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f6a9b-112">Remarks</span></span>  
 <span data-ttu-id="f6a9b-113">Questa funzionalità è attualmente supportata solo per il debug di una destinazione applicazione basata su Silverlight in esecuzione su un computer Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="f6a9b-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a9b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6a9b-114">Requirements</span></span>  
 <span data-ttu-id="f6a9b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6a9b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a9b-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6a9b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6a9b-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6a9b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6a9b-118">**Versioni .NET Framework:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f6a9b-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a9b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6a9b-119">See also</span></span>

- [<span data-ttu-id="f6a9b-120">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="f6a9b-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="f6a9b-121">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f6a9b-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="f6a9b-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f6a9b-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
