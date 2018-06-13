---
title: Metodo ICoreClrDebugTarget::EnumRuntimes
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b5f2227991e38ba66889d7e966ab24e714294c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422582"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="5df74-102">Metodo ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="5df74-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="5df74-103">Enumera i Common Language Runtime (CLR) nel processo specificato in cui è in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="5df74-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5df74-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5df74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5df74-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="5df74-106">[in] ID del processo interno per il quale si vogliono enumerare i runtime.</span><span class="sxs-lookup"><span data-stu-id="5df74-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="5df74-107">Questo sarà `m_dwInternalID` dal corrispondente [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5df74-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="5df74-108">[out] Numero di runtime restituiti in `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="5df74-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="5df74-109">Il valore può essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="5df74-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="5df74-110">[out] Matrice di [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) strutture che rappresentano i runtime caricati nel processo di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="5df74-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5df74-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5df74-111">Return Value</span></span>  
 <span data-ttu-id="5df74-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5df74-112">S_OK</span></span>  
 <span data-ttu-id="5df74-113">Operazione completata.</span><span class="sxs-lookup"><span data-stu-id="5df74-113">Success.</span></span>  
  
 <span data-ttu-id="5df74-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5df74-114">S_FALSE</span></span>  
 <span data-ttu-id="5df74-115">`dwInternalProcessID` non corrisponde a nessun processo in esecuzione nel computer, probabilmente perché il processo è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="5df74-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="5df74-116">`pcRuntimes` e `ppRuntimes` saranno null.</span><span class="sxs-lookup"><span data-stu-id="5df74-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="5df74-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5df74-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5df74-118">Non è possibile allocare memoria sufficiente per `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="5df74-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="5df74-119">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="5df74-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5df74-120">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="5df74-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5df74-121">Note</span><span class="sxs-lookup"><span data-stu-id="5df74-121">Remarks</span></span>  
 <span data-ttu-id="5df74-122">Per liberare la memoria allocata da questo metodo, chiamare il [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="5df74-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5df74-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5df74-123">Requirements</span></span>  
 <span data-ttu-id="5df74-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5df74-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5df74-125">**Intestazione:** coreclrremotedebugginginterfaces. H</span><span class="sxs-lookup"><span data-stu-id="5df74-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5df74-126">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="5df74-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5df74-127">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5df74-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df74-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df74-128">See Also</span></span>  
 [<span data-ttu-id="5df74-129">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="5df74-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
