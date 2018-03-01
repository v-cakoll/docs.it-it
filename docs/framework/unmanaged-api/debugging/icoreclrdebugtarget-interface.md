---
title: Interfaccia ICoreClrDebugTarget
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62d43121efbc039b8fad0b78bed7ec4a655efabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="130e3-102">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="130e3-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="130e3-103">Fornisce metodi che controllano i conteggi dei riferimenti, enumerano i processi e liberano la memoria associata a un debugger è collegato a una destinazione di Silverlight Macintosh remota.</span><span class="sxs-lookup"><span data-stu-id="130e3-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="130e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="130e3-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="130e3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="130e3-105">Methods</span></span>  
  
|<span data-ttu-id="130e3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="130e3-106">Method</span></span>|<span data-ttu-id="130e3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="130e3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="130e3-108">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="130e3-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="130e3-109">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="130e3-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="130e3-110">Metodo ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="130e3-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="130e3-111">Enumera i common language runtime (CLR) nel processo specificato in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="130e3-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="130e3-112">Metodo ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="130e3-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="130e3-113">Libera la memoria allocata dai metodi di enumerazione in questa classe.</span><span class="sxs-lookup"><span data-stu-id="130e3-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="130e3-114">Note</span><span class="sxs-lookup"><span data-stu-id="130e3-114">Remarks</span></span>  
 <span data-ttu-id="130e3-115">Attualmente, questa funzionalità è supportata solo per il debug di applicazioni basate su Silverlight di destinazione in cui è in esecuzione in un computer Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="130e3-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="130e3-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="130e3-116">Requirements</span></span>  
 <span data-ttu-id="130e3-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="130e3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="130e3-118">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="130e3-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="130e3-119">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="130e3-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="130e3-120">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="130e3-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130e3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="130e3-121">See Also</span></span>  
 [<span data-ttu-id="130e3-122">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="130e3-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="130e3-123">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="130e3-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="130e3-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="130e3-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
