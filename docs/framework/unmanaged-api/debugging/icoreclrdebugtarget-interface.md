---
title: Interfaccia ICoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5a3d06f72ed7163a414ef12e9bec650d8b20783
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774280"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="ceeea-102">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="ceeea-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="ceeea-103">Fornisce metodi che controllano i conteggi dei riferimenti, enumerano i processi e liberano la memoria associata a un debugger collegato a una destinazione remota Silverlight Macintosh.</span><span class="sxs-lookup"><span data-stu-id="ceeea-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceeea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ceeea-104">Syntax</span></span>  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ceeea-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="ceeea-105">Methods</span></span>  
  
|<span data-ttu-id="ceeea-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="ceeea-106">Method</span></span>|<span data-ttu-id="ceeea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ceeea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ceeea-108">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="ceeea-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="ceeea-109">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="ceeea-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="ceeea-110">Metodo ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="ceeea-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="ceeea-111">Enumera i common language runtime (CLR) nel processo specificato in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="ceeea-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="ceeea-112">Metodo ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="ceeea-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="ceeea-113">Libera la memoria allocata dai metodi di enumerazione in questa classe.</span><span class="sxs-lookup"><span data-stu-id="ceeea-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceeea-114">Note</span><span class="sxs-lookup"><span data-stu-id="ceeea-114">Remarks</span></span>  
 <span data-ttu-id="ceeea-115">Attualmente, questa funzionalità è supportata solo per il debug di applicazioni basate su Silverlight di destinazione in cui è in esecuzione in un computer Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="ceeea-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceeea-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ceeea-116">Requirements</span></span>  
 <span data-ttu-id="ceeea-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceeea-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceeea-118">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ceeea-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ceeea-119">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ceeea-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ceeea-120">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ceeea-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceeea-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceeea-121">See also</span></span>

- [<span data-ttu-id="ceeea-122">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="ceeea-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="ceeea-123">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ceeea-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="ceeea-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ceeea-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
