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
ms.openlocfilehash: c44a12ef377d29e0b33b8be86aa1d8f0aa9d26bd
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397147"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="e6b66-102">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="e6b66-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="e6b66-103">Fornisce metodi che controllano i conteggi dei riferimenti, enumerano i processi e liberano la memoria associata a un debugger collegato a una destinazione di Silverlight per Macintosh remota.</span><span class="sxs-lookup"><span data-stu-id="e6b66-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6b66-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e6b66-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e6b66-105">Methods</span></span>  
  
|<span data-ttu-id="e6b66-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e6b66-106">Method</span></span>|<span data-ttu-id="e6b66-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6b66-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6b66-108">Metodo ICoreClrDebugTarget::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="e6b66-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="e6b66-109">Enumera i processi in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="e6b66-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="e6b66-110">Metodo ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="e6b66-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="e6b66-111">Enumera i Common Language Runtime (CLR) nel processo specificato in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="e6b66-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="e6b66-112">Metodo ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="e6b66-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="e6b66-113">Libera la memoria allocata dai metodi di enumerazione in questa classe.</span><span class="sxs-lookup"><span data-stu-id="e6b66-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6b66-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="e6b66-114">Remarks</span></span>  
 <span data-ttu-id="e6b66-115">Questa funzionalità è attualmente supportata solo per il debug di una destinazione applicazione basata su Silverlight in esecuzione su un computer Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="e6b66-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6b66-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6b66-116">Requirements</span></span>  
 <span data-ttu-id="e6b66-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b66-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b66-118">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="e6b66-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="e6b66-119">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="e6b66-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="e6b66-120">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="e6b66-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b66-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e6b66-121">See also</span></span>

- [<span data-ttu-id="e6b66-122">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="e6b66-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="e6b66-123">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e6b66-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="e6b66-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e6b66-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
